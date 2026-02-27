<script setup>
import { nextTick, onBeforeUnmount, onMounted, ref, watch } from 'vue'
import { siteData } from '@/assets/data'

const headerData = siteData.header
const { navItems } = headerData

const socialLinksById = Object.fromEntries(
  headerData.mobileSocialItems.map((item) => [item.id, item]),
)

const isMobileMenuOpen = ref(false)
const activeHash = ref('')
let previousBodyOverflow = ''
let pendingAnchorScrollTimeout = null

const syncHash = () => {
  if (typeof window === 'undefined') return
  activeHash.value = window.location.hash || ''
}

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const handleMenuItemClick = () => {
  closeMobileMenu()
}

const isAnchorHref = (href) => typeof href === 'string' && href.startsWith('#')

const scrollToAnchor = (href, options = {}) => {
  if (typeof window === 'undefined' || typeof document === 'undefined') return false
  if (!isAnchorHref(href)) return false

  const { behavior = 'smooth', updateHistory = true } = options
  const target = document.querySelector(href)

  if (updateHistory && window.location.hash !== href) {
    window.history.pushState(null, '', href)
  }

  if (!target) {
    syncHash()
    return false
  }

  target.scrollIntoView({ behavior, block: 'start' })
  activeHash.value = href
  return true
}

const clearPendingAnchorScroll = () => {
  if (pendingAnchorScrollTimeout !== null && typeof window !== 'undefined') {
    window.clearTimeout(pendingAnchorScrollTimeout)
    pendingAnchorScrollTimeout = null
  }
}

const scheduleAnchorScroll = async (href, closeMenuFirst = false, options = {}) => {
  if (!isAnchorHref(href)) return

  clearPendingAnchorScroll()

  if (closeMenuFirst && isMobileMenuOpen.value) {
    closeMobileMenu()
    await nextTick()

    pendingAnchorScrollTimeout = window.setTimeout(() => {
      pendingAnchorScrollTimeout = null
      scrollToAnchor(href, options)
    }, 180)
    return
  }

  scrollToAnchor(href, options)
}

const handleNavLinkClick = (event, href) => {
  if (!isAnchorHref(href)) return
  event.preventDefault()
  void scheduleAnchorScroll(href, false)
}

const handleMobileLinkClick = (event, href) => {
  if (!isAnchorHref(href)) {
    handleMenuItemClick()
    return
  }

  event.preventDefault()
  void scheduleAnchorScroll(href, true)
}

const isMobileItemActive = (href) => {
  if (!href.startsWith('#')) return false
  const current = activeHash.value || '#contacts'
  return current === href
}

const handleHashChange = () => {
  if (typeof window === 'undefined') return
  syncHash()

  if (window.location.hash) {
    void scheduleAnchorScroll(window.location.hash, false, {
      updateHistory: false,
    })
  }
}

const handleKeydown = (event) => {
  if (event.key === 'Escape' && isMobileMenuOpen.value) {
    closeMobileMenu()
  }
}

const handleResize = () => {
  if (typeof window === 'undefined') return
  if (window.innerWidth >= 1024 && isMobileMenuOpen.value) {
    closeMobileMenu()
  }
  syncHash()
}

watch(isMobileMenuOpen, (opened) => {
  if (typeof document === 'undefined') return

  if (opened) {
    previousBodyOverflow = document.body.style.overflow
    document.body.style.overflow = 'hidden'
  } else {
    document.body.style.overflow = previousBodyOverflow
  }
})

onMounted(() => {
  syncHash()
  if (typeof window !== 'undefined') {
    window.addEventListener('keydown', handleKeydown)
    window.addEventListener('resize', handleResize)
    window.addEventListener('hashchange', handleHashChange)

    if (window.location.hash) {
      requestAnimationFrame(() => {
        requestAnimationFrame(() => {
          void scheduleAnchorScroll(window.location.hash, false, {
            updateHistory: false,
          })
        })
      })
    }
  }
})

onBeforeUnmount(() => {
  if (typeof window !== 'undefined') {
    window.removeEventListener('keydown', handleKeydown)
    window.removeEventListener('resize', handleResize)
    window.removeEventListener('hashchange', handleHashChange)
    clearPendingAnchorScroll()
  }

  if (typeof document !== 'undefined') {
    document.body.style.overflow = previousBodyOverflow
  }
})
</script>

<template>
  <!-- HEADER (фиксированная, впереди всего) -->
  <header class="fixed left-0 top-0 z-[1000] w-full bg-[#02030A] shadow-[0_8px_28px_rgba(0,0,0,0.24)]">
    <div class="mx-auto max-w-[1720px] px-4 sm:px-6 lg:px-10">
      <div class="relative flex h-[74px] items-center justify-between lg:h-[88px]">
        <a :href="headerData.brandHref" class="flex shrink-0 items-center gap-3 text-white" :aria-label="headerData.brandName">
          <img
            :src="siteData.assets.images.logo"
            :alt="headerData.brandName"
            class="h-11 w-auto rounded-full sm:h-[52px] lg:h-[58px]"
            draggable="false"
          />
          <span class="text-[20px] font-semibold leading-none tracking-[-0.02em] sm:text-[24px] lg:text-[26px]">
            {{ headerData.brandName }}
          </span>
        </a>

        <!-- Desktop nav -->
        <nav
          class="absolute left-1/2 top-1/2 hidden -translate-x-1/2 -translate-y-1/2 items-center gap-4 lg:flex xl:gap-8 2xl:gap-14"
          :aria-label="headerData.aria.desktopNav"
        >
          <a
            v-for="item in navItems"
            :key="item.href"
            :href="item.href"
            class="text-[15px] font-medium text-[#A8ABC3] transition-colors duration-200 hover:text-[#736CFF] xl:text-[17px] 2xl:text-[20px]"
            @click="handleNavLinkClick($event, item.href)"
          >
            {{ item.label }}
          </a>
        </nav>

        <!-- Mobile burger -->
        <button
          type="button"
          class="relative z-[1001] inline-flex h-11 w-11 shrink-0 items-center justify-center rounded-full border border-white/15 bg-white/[0.03] text-white transition hover:bg-white/5 active:scale-[0.98] lg:hidden"
          :aria-label="isMobileMenuOpen ? headerData.aria.closeMenu : headerData.aria.openMenu"
          :aria-expanded="isMobileMenuOpen"
          aria-controls="mobile-menu"
          @click="toggleMobileMenu"
        >
          <svg
            v-if="!isMobileMenuOpen"
            viewBox="0 0 24 24"
            class="h-6 w-6"
            fill="none"
            stroke="currentColor"
            stroke-width="1.9"
            stroke-linecap="round"
          >
            <path d="M4 7h16" />
            <path d="M4 12h16" />
            <path d="M4 17h16" />
          </svg>

          <svg
            v-else
            viewBox="0 0 24 24"
            class="h-6 w-6"
            fill="none"
            stroke="currentColor"
            stroke-width="2.2"
            stroke-linecap="round"
          >
            <path d="M5 5l14 14" />
            <path d="M19 5 5 19" />
          </svg>
        </button>
      </div>
    </div>
  </header>

  <!-- MOBILE FULLSCREEN MENU (как на скрине) -->
  <Teleport to="body">
    <Transition
      enter-active-class="transition-opacity duration-200 ease-out"
      enter-from-class="opacity-0"
      enter-to-class="opacity-100"
      leave-active-class="transition-opacity duration-150 ease-in"
      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
    >
      <div
        v-if="isMobileMenuOpen"
        id="mobile-menu"
        class="fixed inset-0 z-[1100] bg-black lg:hidden"
        role="dialog"
        aria-modal="true"
        :aria-label="headerData.aria.mobileDialog"
      >
        <!-- Верхняя панель (логотип + крестик), как на изображении -->
        <div class="mx-auto max-w-[1720px] px-4 sm:px-6">
          <div class="flex h-[74px] items-center justify-between">
            <a
              :href="headerData.brandHref"
              class="flex shrink-0 items-center gap-3 text-white"
              :aria-label="headerData.brandName"
              @click="handleMenuItemClick"
            >
              <img
                :src="siteData.assets.images.logo"
                :alt="headerData.brandName"
                class="h-11 w-auto rounded-full"
                draggable="false"
              />
              <span class="text-[20px] font-semibold leading-none tracking-[-0.02em]">
                {{ headerData.brandName }}
              </span>
            </a>

            <button
              type="button"
              class="inline-flex h-11 w-11 items-center justify-center text-white"
              :aria-label="headerData.aria.closeMenu"
              @click="closeMobileMenu"
            >
              <svg viewBox="0 0 24 24" class="h-8 w-8" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round">
                <path d="M5 5l14 14" />
                <path d="M19 5 5 19" />
              </svg>
            </button>
          </div>
        </div>

        <!-- Меню по центру -->
        <div class="flex h-[calc(100vh-74px)] flex-col">
          <div class="flex flex-1 items-center justify-center px-6">
            <nav class="-mt-6 flex flex-col items-center gap-5 text-center" :aria-label="headerData.aria.mobileNav">
              <a
                v-for="item in navItems"
                :key="item.href"
                :href="item.href"
                class="text-[18px] leading-[1.2] tracking-[-0.02em] transition-colors"
                :class="
                  isMobileItemActive(item.href)
                    ? 'font-semibold text-white'
                    : 'font-medium text-white/60 hover:text-white'
                "
                @click="handleMobileLinkClick($event, item.href)"
              >
                {{ item.label }}
              </a>
            </nav>
          </div>

          <!-- Иконки снизу по центру -->
          <div class="pb-10">
            <div class="flex items-center justify-center gap-4">
              <a
                :href="socialLinksById.whatsapp?.href || '#'"
                :aria-label="socialLinksById.whatsapp?.label || 'WhatsApp'"
                class="inline-flex h-11 w-11 items-center justify-center rounded-full bg-[#6A5EFD] text-black shadow-[0_10px_24px_rgba(106,94,253,0.35)]"
                @click.prevent
              >
                <svg
                  viewBox="0 0 24 24"
                  class="h-[18px] w-[18px]"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.9"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <path d="M20 11.5A8 8 0 0 1 8.6 18.7L4.5 20l1.4-3.9A8 8 0 1 1 20 11.5Z" />
                  <path
                    d="M9.2 9.1c.2-.5.4-.5.7-.5h.5c.1 0 .4.1.5.4l.8 1.8c.1.2 0 .4-.1.6l-.4.5c-.1.1-.2.2-.1.4.2.4.8 1.3 1.8 1.8.2.1.3 0 .4-.1l.5-.6c.2-.2.4-.2.6-.1l1.7.8c.3.1.4.4.4.5v.5c0 .3-.2.5-.4.6-.5.2-1.1.4-1.8.2-1-.3-2.1-.9-3.1-1.9-1-1-1.6-2.1-1.9-3.1-.2-.8 0-1.4.2-1.8Z"
                  />
                </svg>
              </a>

              <a
                :href="socialLinksById.instagram?.href || '#'"
                :aria-label="socialLinksById.instagram?.label || 'Instagram'"
                class="inline-flex h-11 w-11 items-center justify-center rounded-full bg-[#6A5EFD] text-black shadow-[0_10px_24px_rgba(106,94,253,0.35)]"
                @click.prevent
              >
                <svg
                  viewBox="0 0 24 24"
                  class="h-[18px] w-[18px]"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <rect x="4" y="4" width="16" height="16" rx="5" />
                  <circle cx="12" cy="12" r="3.5" />
                  <circle cx="17" cy="7" r="0.9" fill="currentColor" stroke="none" />
                </svg>
              </a>

              <a
                :href="socialLinksById.telegram?.href || '#'"
                :aria-label="socialLinksById.telegram?.label || 'Telegram'"
                class="inline-flex h-11 w-11 items-center justify-center rounded-full bg-[#6A5EFD] text-black shadow-[0_10px_24px_rgba(106,94,253,0.35)]"
                @click.prevent
              >
                <svg viewBox="0 0 24 24" class="h-[18px] w-[18px] translate-x-[1px]" fill="currentColor">
                  <path d="M20.8 4.6c.4-.2.8.2.7.6l-2.8 13c-.1.5-.7.7-1.1.5l-4.1-3-2.1 2c-.2.2-.4.3-.7.3l.4-4.3 7.8-7.1-9.7 6.1-3.9-1.2c-.6-.2-.6-1 .1-1.3l15.4-5.6Z" />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
    </Transition>
  </Teleport>
</template>

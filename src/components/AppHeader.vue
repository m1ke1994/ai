<script setup>
import { computed, onBeforeUnmount, onMounted, ref, watch } from 'vue'

const navItems = [
  { label: 'Преимущества', href: '#advantages' },
  { label: 'Этапы', href: '#steps' },
  { label: 'Отзывы', href: '#reviews' },
  { label: 'Контакты', href: '#contacts' },
  { label: 'Тарифы', href: '#pricing' },
]

const authItems = [
  { label: 'Логин', href: '/login' },
  { label: 'Регистрация', href: '/register' },
]

const mobileItems = computed(() => [...navItems, ...authItems])

const isMobileMenuOpen = ref(false)
const activeHash = ref('')
let previousBodyOverflow = ''

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

const isMobileItemActive = (href) => {
  if (!href.startsWith('#')) return false
  const current = activeHash.value || '#contacts'
  return current === href
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
    window.addEventListener('hashchange', syncHash)
  }
})

onBeforeUnmount(() => {
  if (typeof window !== 'undefined') {
    window.removeEventListener('keydown', handleKeydown)
    window.removeEventListener('resize', handleResize)
    window.removeEventListener('hashchange', syncHash)
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
        <a href="/" class="flex shrink-0 items-center gap-2.5 text-white" aria-label="MoonAI">
          <span class="inline-flex h-6 w-[25px] items-center justify-center sm:h-7 sm:w-[29px]" aria-hidden="true">
            <svg viewBox="0 0 86 83" class="h-full w-auto" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M12.82 67.1881C10.7204 67.1881 8.64538 66.6222 6.82464 65.556C1.16559 62.2508 -0.74537 54.9514 2.56805 49.2924C3.83108 47.1354 5.81585 45.3884 8.14509 44.3797C14.0912 41.8126 17.6671 35.6696 16.9699 29.2396C16.6993 26.73 17.2406 24.2285 18.5364 22.0059C20.6606 18.3726 24.5974 16.1172 28.8129 16.1172C30.9125 16.1172 32.9875 16.6831 34.8083 17.7493C40.4673 21.0627 42.3783 28.3621 39.0649 34.0211C37.8018 36.1781 35.817 37.9251 33.4796 38.9338C27.5335 41.4927 23.9576 47.6275 24.6466 54.0657C24.8352 55.8372 24.7204 58.5273 23.0965 61.3076C20.9723 64.9327 17.0355 67.1881 12.82 67.1881Z" fill="#6A5EFD" />
              <path d="M43.0914 67.1533C40.9919 67.1533 38.9169 66.5874 37.0961 65.5212C31.4371 62.2078 29.5261 54.9085 32.8395 49.2494C34.1026 47.0924 36.0873 45.3455 38.4248 44.3367C44.3709 41.7696 47.9467 35.6349 47.2578 29.2049C47.0692 27.4333 47.184 24.7432 48.8161 21.9629C50.9403 18.3296 54.877 16.0742 59.0926 16.0742C61.1922 16.0742 63.2672 16.6401 65.0879 17.7063C70.747 21.0197 72.658 28.3191 69.3445 33.9782C68.0815 36.1352 66.0967 37.8821 63.7593 38.8909C57.8132 41.4497 54.2373 47.5845 54.9262 54.0227C55.1149 55.7942 55.0001 58.4843 53.3762 61.2646C51.2438 64.8979 47.307 67.1533 43.0914 67.1533Z" fill="#6A5EFD" />
              <path d="M73.5121 67.1536C71.4126 67.1536 69.3376 66.5877 67.5168 65.5215C64.7365 63.8894 62.8338 61.3879 62.0218 58.2713C61.2099 55.1547 61.6363 52.0382 63.2602 49.2578C65.3844 45.6246 69.3212 43.3691 73.5368 43.3691C75.6363 43.3691 77.7113 43.935 79.5321 45.0012C82.3124 46.6251 84.2151 49.1348 85.0271 52.2596C85.839 55.3762 85.4126 58.4928 83.7887 61.2731C81.6645 64.8982 77.7277 67.1536 73.5121 67.1536Z" fill="#6A5EFD" />
            </svg>
          </span>
          <span class="text-[18px] font-semibold leading-none tracking-[-0.02em] sm:text-[22px]">
            MoonAI
          </span>
        </a>

        <!-- Desktop nav -->
        <nav
          class="absolute left-1/2 top-1/2 hidden -translate-x-1/2 -translate-y-1/2 items-center gap-8 lg:flex xl:gap-14"
          aria-label="Основная навигация"
        >
          <a
            v-for="item in navItems"
            :key="item.href"
            :href="item.href"
            class="text-[20px] font-medium text-[#A8ABC3] transition-colors duration-200 hover:text-[#736CFF]"
          >
            {{ item.label }}
          </a>
        </nav>

        <!-- Desktop auth -->
        <div class="hidden items-center gap-8 lg:flex">
          <a href="/login" class="text-[20px] font-medium text-[#B4B7CD] transition-colors duration-200 hover:text-white">
            Логин
          </a>
          <a
            href="/register"
            class="inline-flex h-10 items-center rounded-xl px-4 text-[20px] font-medium text-[#ECEEFA] transition duration-200 hover:text-white"
          >
            Регистрация
          </a>
        </div>

        <!-- Mobile burger -->
        <button
          type="button"
          class="relative z-[1001] inline-flex h-11 w-11 shrink-0 items-center justify-center rounded-full border border-white/15 bg-white/[0.03] text-white transition hover:bg-white/5 active:scale-[0.98] lg:hidden"
          :aria-label="isMobileMenuOpen ? 'Закрыть меню' : 'Открыть меню'"
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
        aria-label="Мобильное меню"
      >
        <!-- Верхняя панель (логотип + крестик), как на изображении -->
        <div class="mx-auto max-w-[1720px] px-4 sm:px-6">
          <div class="flex h-[74px] items-center justify-between">
            <a
              href="/"
              class="flex shrink-0 items-center gap-2.5 text-white"
              aria-label="MoonAI"
              @click="handleMenuItemClick"
            >
              <span class="inline-flex h-6 w-[25px] items-center justify-center" aria-hidden="true">
                <svg viewBox="0 0 86 83" class="h-full w-auto" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M12.82 67.1881C10.7204 67.1881 8.64538 66.6222 6.82464 65.556C1.16559 62.2508 -0.74537 54.9514 2.56805 49.2924C3.83108 47.1354 5.81585 45.3884 8.14509 44.3797C14.0912 41.8126 17.6671 35.6696 16.9699 29.2396C16.6993 26.73 17.2406 24.2285 18.5364 22.0059C20.6606 18.3726 24.5974 16.1172 28.8129 16.1172C30.9125 16.1172 32.9875 16.6831 34.8083 17.7493C40.4673 21.0627 42.3783 28.3621 39.0649 34.0211C37.8018 36.1781 35.817 37.9251 33.4796 38.9338C27.5335 41.4927 23.9576 47.6275 24.6466 54.0657C24.8352 55.8372 24.7204 58.5273 23.0965 61.3076C20.9723 64.9327 17.0355 67.1881 12.82 67.1881Z" fill="#6A5EFD" />
                  <path d="M43.0914 67.1533C40.9919 67.1533 38.9169 66.5874 37.0961 65.5212C31.4371 62.2078 29.5261 54.9085 32.8395 49.2494C34.1026 47.0924 36.0873 45.3455 38.4248 44.3367C44.3709 41.7696 47.9467 35.6349 47.2578 29.2049C47.0692 27.4333 47.184 24.7432 48.8161 21.9629C50.9403 18.3296 54.877 16.0742 59.0926 16.0742C61.1922 16.0742 63.2672 16.6401 65.0879 17.7063C70.747 21.0197 72.658 28.3191 69.3445 33.9782C68.0815 36.1352 66.0967 37.8821 63.7593 38.8909C57.8132 41.4497 54.2373 47.5845 54.9262 54.0227C55.1149 55.7942 55.0001 58.4843 53.3762 61.2646C51.2438 64.8979 47.307 67.1533 43.0914 67.1533Z" fill="#6A5EFD" />
                  <path d="M73.5121 67.1536C71.4126 67.1536 69.3376 66.5877 67.5168 65.5215C64.7365 63.8894 62.8338 61.3879 62.0218 58.2713C61.2099 55.1547 61.6363 52.0382 63.2602 49.2578C65.3844 45.6246 69.3212 43.3691 73.5368 43.3691C75.6363 43.3691 77.7113 43.935 79.5321 45.0012C82.3124 46.6251 84.2151 49.1348 85.0271 52.2596C85.839 55.3762 85.4126 58.4928 83.7887 61.2731C81.6645 64.8982 77.7277 67.1536 73.5121 67.1536Z" fill="#6A5EFD" />
                </svg>
              </span>
              <span class="text-[18px] font-semibold leading-none tracking-[-0.02em]">
                MoonAI
              </span>
            </a>

            <button
              type="button"
              class="inline-flex h-11 w-11 items-center justify-center text-white"
              aria-label="Закрыть меню"
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
            <nav class="-mt-6 flex flex-col items-center gap-5 text-center" aria-label="Мобильная навигация">
              <a
                v-for="item in mobileItems"
                :key="item.href"
                :href="item.href"
                class="text-[18px] leading-[1.2] tracking-[-0.02em] transition-colors"
                :class="
                  isMobileItemActive(item.href)
                    ? 'font-semibold text-white'
                    : 'font-medium text-white/60 hover:text-white'
                "
                @click="handleMenuItemClick"
              >
                {{ item.label }}
              </a>
            </nav>
          </div>

          <!-- Иконки снизу по центру -->
          <div class="pb-10">
            <div class="flex items-center justify-center gap-4">
              <a
                href="#"
                aria-label="WhatsApp"
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
                href="#"
                aria-label="Instagram"
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
                href="#"
                aria-label="Telegram"
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
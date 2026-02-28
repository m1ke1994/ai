<template>
  <section
    id="contacts"
    class="relative scroll-mt-[92px] overflow-hidden bg-[#01020a] pt-4 pb-0 sm:pt-5 sm:pb-0 lg:scroll-mt-[104px] lg:pt-6 lg:pb-0"
  >
    <img
      :src="contactsData.media.sectionBackground.src"
      alt=""
      aria-hidden="true"
      class="pointer-events-none absolute inset-0 h-full w-full object-cover"
      draggable="false"
    />

    <div
      aria-hidden="true"
      class="absolute inset-0 bg-[linear-gradient(180deg,rgba(4,5,18,0.72)_0%,rgba(7,9,28,0.58)_38%,rgba(7,9,28,0.84)_100%)]"
    ></div>

    <div
      aria-hidden="true"
      class="absolute inset-0 opacity-[0.18]"
      style="
        background-image: repeating-linear-gradient(
          125deg,
          rgba(194, 202, 255, 0.18) 0px,
          rgba(194, 202, 255, 0.18) 2px,
          transparent 2px,
          transparent 14px
        );
      "
    ></div>

    <div class="relative z-10 mx-auto max-w-[1840px] px-4">
      <div class="relative min-h-[420px] overflow-hidden rounded-[36px] bg-[rgba(9,12,41,0.18)] xl:min-h-[560px]">
        <div
          class="relative z-10 grid items-start gap-8 p-6 pb-0 sm:p-10 sm:pb-0 lg:min-h-0 lg:grid-cols-1 lg:items-start lg:px-10 lg:pt-12 lg:pb-0 xl:min-h-[560px] xl:grid-cols-[minmax(0,1fr)_760px] xl:items-stretch xl:px-20 xl:pt-20 xl:pb-0"
        >
          <!-- Р›Р•Р’Р«Р™ Р‘Р›РћРљ -->
          <div class="pt-2 lg:self-start lg:pt-4 xl:pt-14">
            <h2
              class="max-w-[820px] text-[34px] font-semibold leading-[0.96] tracking-[-0.035em] text-white sm:text-[48px] lg:text-[56px] xl:text-[68px]"
            >
              {{ contactsData.title }}
              <span
                class="block bg-[linear-gradient(90deg,#7A6EFF_0%,#9D96FF_100%)] bg-clip-text text-transparent"
              >
                {{ contactsData.subtitle }}
              </span>
              <span class="block">{{ contactsData.meta.headingLine3 }}</span>
            </h2>

            <p
              class="mt-6 max-w-[620px] text-[15px] leading-[1.45] tracking-[-0.02em] text-[#ECEAFF] sm:text-[18px] lg:text-[20px] xl:mt-8 xl:text-[22px]"
            >
              {{ contactsData.description }}
            </p>
          </div>

          <!-- РџР РђР’Р«Р™ Р‘Р›РћРљ (Р’РњР•РЎРўРћ РљРќРћРџРљР вЂ” РљРђРќРђР›Р« РЎР’РЇР—Р) -->
          <div class="lg:flex lg:h-full lg:items-end lg:justify-start xl:justify-end">
            <div
              class="relative w-full max-w-full overflow-hidden rounded-[32px] shadow-[0_30px_80px_rgba(34,24,89,0.38)] lg:max-w-[760px] xl:w-[760px]"
            >
              <img
                :src="contactsData.media.cardBackground.src"
                alt=""
                aria-hidden="true"
                class="pointer-events-none absolute inset-0 h-full w-full object-cover"
                draggable="false"
              />

              <div
                aria-hidden="true"
                class="absolute inset-0 bg-[linear-gradient(180deg,rgba(121,107,255,0.62)_0%,rgba(129,117,255,0.58)_45%,rgba(115,105,247,0.68)_100%)]"
              ></div>

              <div
                aria-hidden="true"
                class="absolute inset-0 opacity-[0.10]"
                style="
                  background-image: repeating-linear-gradient(
                    130deg,
                    rgba(255,255,255,0.35) 0px,
                    rgba(255,255,255,0.35) 2px,
                    transparent 2px,
                    transparent 16px
                  );
                "
              ></div>

              <div class="relative z-10 px-6 py-7 sm:px-8 sm:py-8 lg:px-10 lg:py-12 xl:px-14 xl:py-16">
                <h3
                  class="max-w-[560px] text-[26px] font-semibold leading-[1.1] tracking-[-0.03em] text-white sm:text-[32px] lg:text-[38px] xl:text-[44px]"
                >
                  {{ cardData.titleLine1 }}
                  <span class="block">{{ cardData.titleLine2 }}</span>
                </h3>

                <p
                  class="mt-5 max-w-[560px] text-[14px] leading-[1.45] tracking-[-0.02em] text-[#ECEAFF] sm:text-[16px] lg:text-[18px] xl:mt-6 xl:text-[20px]"
                >
                  {{ cardData.description }}
                </p>

                <div class="mt-8 grid gap-3 sm:gap-4 lg:mt-10 sm:grid-cols-2">
                  <a
                    v-for="item in messengerItems"
                    :key="item.id"
                    :href="item.href"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="group inline-flex h-16 w-full items-center justify-center gap-3 rounded-[20px]
                           border border-white/12 bg-white/10 px-6 text-[16px] font-medium tracking-[-0.02em] text-white
                           backdrop-blur-md shadow-[0_16px_40px_rgba(11,12,19,0.30)] transition
                           hover:bg-white/15 active:scale-[0.99]
                           sm:h-[72px] lg:h-[82px] lg:rounded-[22px] lg:text-[18px] xl:h-[92px] xl:rounded-[24px] xl:text-[20px]"
                    :aria-label="item.ariaLabel"
                  >
                    <span
                      class="inline-flex h-11 w-11 items-center justify-center rounded-[16px] border border-white/12 bg-[#1E2030]/55 transition group-hover:bg-[#1E2030]/70 sm:h-12 sm:w-12"
                      aria-hidden="true"
                    >
                      <img
                        :src="item.icon.src"
                        :alt="item.icon.alt"
                        class="h-6 w-6 object-contain"
                        loading="lazy"
                        draggable="false"
                      />
                    </span>
                    <span>{{ item.label }}</span>
                  </a>
                </div>

                <p class="mt-6 text-xs text-white/70 sm:text-sm">
                  {{ cardData.responseTime }}
                </p>
              </div>
            </div>
          </div>
          <!-- /РџР РђР’Р«Р™ Р‘Р›РћРљ -->
        </div>
      </div>
    </div>
  </section>

  <Teleport to="body">
    <Transition
      enter-active-class="transition duration-200 ease-out"
      enter-from-class="opacity-0"
      enter-to-class="opacity-100"
      leave-active-class="transition duration-150 ease-in"
      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
    >
      <div
        v-if="isFormOpen"
        class="fixed inset-0 z-[230] bg-black/70 p-4 backdrop-blur-sm sm:p-6"
        role="dialog"
        aria-modal="true"
        aria-labelledby="contact-form-title"
        @click.self="closeForm"
      >
        <div class="flex min-h-full items-center justify-center">
          <div class="w-full max-w-[620px] overflow-hidden rounded-[24px] border border-white/10 bg-[#101325] shadow-[0_25px_80px_rgba(0,0,0,0.45)]">
            <div class="flex items-start justify-between gap-4 border-b border-white/10 px-5 py-5 sm:px-7">
              <div>
                <h3 id="contact-form-title" class="text-xl font-semibold tracking-[-0.02em] text-white sm:text-2xl">
                  {{ formData.title }}
                </h3>
                <p class="mt-2 text-sm text-[#BDC1E2] sm:text-base">
                  {{ formData.subtitle }}
                </p>
              </div>

              <button
                type="button"
                class="inline-flex h-10 w-10 shrink-0 items-center justify-center rounded-full border border-white/10 bg-white/5 text-white transition hover:bg-white/10 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-white/60"
                :aria-label="formData.closeAriaLabel"
                @click="closeForm"
              >
                <svg viewBox="0 0 20 20" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.8">
                  <path d="M5 5l10 10M15 5 5 15" stroke-linecap="round" />
                </svg>
              </button>
            </div>

            <form class="space-y-4 px-5 py-5 sm:px-7 sm:py-6" @submit.prevent="submitForm">
              <label class="block">
                <span class="mb-2 block text-sm font-medium text-[#E5E7FF]">{{ formFieldsBySlug.name.label }}</span>
                <input
                  v-model.trim="form.name"
                  type="text"
                  class="w-full rounded-[14px] border border-white/10 bg-white/5 px-4 py-3 text-white outline-none placeholder:text-[#9AA0C8] focus:border-white/25 focus-visible:ring-2 focus-visible:ring-white/15"
                  :placeholder="formFieldsBySlug.name.placeholder"
                  required
                />
              </label>

              <label class="block">
                <span class="mb-2 block text-sm font-medium text-[#E5E7FF]">{{ formFieldsBySlug.contact.label }}</span>
                <input
                  v-model.trim="form.contact"
                  type="text"
                  class="w-full rounded-[14px] border border-white/10 bg-white/5 px-4 py-3 text-white outline-none placeholder:text-[#9AA0C8] focus:border-white/25 focus-visible:ring-2 focus-visible:ring-white/15"
                  :placeholder="formFieldsBySlug.contact.placeholder"
                  required
                />
              </label>

              <label class="block">
                <span class="mb-2 block text-sm font-medium text-[#E5E7FF]">{{ formFieldsBySlug.comment.label }}</span>
                <textarea
                  v-model.trim="form.comment"
                  rows="4"
                  class="w-full resize-none rounded-[14px] border border-white/10 bg-white/5 px-4 py-3 text-white outline-none placeholder:text-[#9AA0C8] focus:border-white/25 focus-visible:ring-2 focus-visible:ring-white/15"
                  :placeholder="formFieldsBySlug.comment.placeholder"
                ></textarea>
              </label>

              <div class="pt-2">
                <button
                  type="submit"
                  class="inline-flex h-12 w-full items-center justify-center rounded-[14px] border border-white/20 bg-[linear-gradient(90deg,#6F63FF_0%,#8B7FFF_100%)] px-5 text-base font-medium text-white shadow-[0_14px_36px_rgba(92,80,255,0.35)] transition hover:opacity-95 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-white/40"
                >
                  {{ formData.submitLabel }}
                </button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </Transition>
  </Teleport>
</template>

<script setup>
import { onBeforeUnmount, onMounted, ref, watch } from 'vue'
import { siteData } from '@/assets/data'

const contactsData = siteData.contacts
const cardData = contactsData.meta.card
const formData = contactsData.meta.form
const messengerItems = contactsData.items
const formFieldsBySlug = Object.fromEntries(formData.fields.map((field) => [field.slug, field]))
const CONTACT_FORM_OPEN_EVENT = siteData.events.contactFormOpen

const isFormOpen = ref(false)
let previousBodyOverflow = ''
const form = ref({
  name: '',
  contact: '',
  comment: '',
})

const openForm = () => {
  isFormOpen.value = true
}

const closeForm = () => {
  isFormOpen.value = false
}

const submitForm = () => {
  closeForm()
}

const handleOpenFormEvent = () => {
  openForm()
}

const handleKeydown = (event) => {
  if (event.key === 'Escape' && isFormOpen.value) {
    closeForm()
  }
}

watch(isFormOpen, (opened) => {
  if (typeof document === 'undefined') return

  if (opened) {
    previousBodyOverflow = document.body.style.overflow
    document.body.style.overflow = 'hidden'
  } else {
    document.body.style.overflow = previousBodyOverflow
    form.value = { name: '', contact: '', comment: '' }
  }
})

onMounted(() => {
  if (typeof window !== 'undefined') {
    window.addEventListener('keydown', handleKeydown)
    window.addEventListener(CONTACT_FORM_OPEN_EVENT, handleOpenFormEvent)
  }
})

onBeforeUnmount(() => {
  if (typeof window !== 'undefined') {
    window.removeEventListener('keydown', handleKeydown)
    window.removeEventListener(CONTACT_FORM_OPEN_EVENT, handleOpenFormEvent)
  }
  if (typeof document !== 'undefined') {
    document.body.style.overflow = previousBodyOverflow
  }
})
</script>

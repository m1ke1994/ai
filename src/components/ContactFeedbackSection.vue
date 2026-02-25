<template>
  <section id="contacts" class="relative scroll-mt-[110px] overflow-hidden rounded-[40px] bg-[#01020a] pt-8 pb-0 sm:pt-10 sm:pb-0 lg:pt-12 lg:pb-0">
    <img
      src="/bg-fon.png"
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
      <div
        class="relative overflow-hidden rounded-[36px] bg-[rgba(9,12,41,0.18)] min-h-[420px] lg:min-h-[560px]"
      >
        <div
          class="relative z-10 grid items-start gap-8 p-6 pb-0 sm:p-10 sm:pb-0 lg:min-h-[560px] lg:grid-cols-[minmax(0,1fr)_760px] lg:items-stretch lg:px-20 lg:pt-20 lg:pb-0"
        >
          <div class="pt-2 lg:self-start lg:pt-14">
            <h2
              class="max-w-[700px] text-[38px] font-semibold leading-[0.96] tracking-[-0.035em] text-white sm:text-[52px] lg:text-[72px]"
            >
              Получите бесплатное
              <span
                class="block bg-[linear-gradient(90deg,#7A6EFF_0%,#9D96FF_100%)] bg-clip-text text-transparent"
              >
                установление
              </span>
              <span class="block">кастомного ИИ</span>
            </h2>
          </div>

          <div class="lg:flex lg:h-full lg:items-end lg:justify-end">
            <div
              class="relative w-full overflow-hidden rounded-[32px] shadow-[0_30px_80px_rgba(34,24,89,0.38)] lg:w-[760px]"
            >
              <img
                src="/bg.png"
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

              <div class="relative z-10 px-6 py-7 sm:px-8 sm:py-8 lg:px-14 lg:py-16">
                <h3
                  class="max-w-[520px] text-[30px] font-semibold leading-[1.1] tracking-[-0.03em] text-white sm:text-[36px] lg:text-[52px]"
                >
                  Оставьте заявку, и мы
                  <span class="block">свяжемся с вами</span>
                </h3>

                <p
                  class="mt-6 max-w-[560px] text-[15px] leading-[1.35] tracking-[-0.02em] text-[#ECEAFF] sm:text-[18px] lg:mt-8 lg:text-[26px]"
                >
                  Эксперт учтёт все бизнес-аспекты и тонкости — вы платите только за диалоги
                </p>

                <div class="mt-8 flex flex-wrap gap-3 sm:gap-4 lg:mt-10 lg:flex-nowrap">
                  <button
                    type="button"
                    class="inline-flex h-16 w-full items-center justify-center rounded-[20px] border border-white/10 bg-[#1E2030] px-6 text-[18px] font-medium tracking-[-0.02em] text-white shadow-[0_16px_40px_rgba(11,12,19,0.35)] transition hover:bg-[#23263b] sm:h-[72px] lg:h-[92px] lg:w-[378px] lg:rounded-[24px] lg:text-[22px]"
                    @click="openForm"
                  >
                    Оставить заявку
                  </button>

                  <a
                    href="#"
                    class="group inline-flex h-16 w-16 items-center justify-center rounded-[18px] border border-white/10 bg-white/10 text-white backdrop-blur-sm transition hover:bg-white/15 sm:h-[72px] sm:w-[72px] lg:h-[92px] lg:w-[92px] lg:rounded-[22px]"
                    aria-label="Instagram"
                    @click.prevent
                  >
                    <svg viewBox="0 0 24 24" class="h-7 w-7 lg:h-9 lg:w-9" fill="none" stroke="currentColor" stroke-width="1.8">
                      <rect x="4" y="4" width="16" height="16" rx="5" />
                      <circle cx="12" cy="12" r="3.7" />
                      <circle cx="17.2" cy="6.8" r="0.9" fill="currentColor" stroke="none" />
                    </svg>
                  </a>

                  <a
                    href="#"
                    class="group inline-flex h-16 w-16 items-center justify-center rounded-[18px] border border-white/10 bg-white/10 text-white backdrop-blur-sm transition hover:bg-white/15 sm:h-[72px] sm:w-[72px] lg:h-[92px] lg:w-[92px] lg:rounded-[22px]"
                    aria-label="WhatsApp"
                    @click.prevent
                  >
                    <svg viewBox="0 0 24 24" class="h-7 w-7 lg:h-9 lg:w-9" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
                      <path d="M20 11.5A8 8 0 0 1 8.6 18.7L4.5 20l1.4-3.9A8 8 0 1 1 20 11.5Z" />
                      <path d="M9.2 9.1c.2-.5.4-.5.7-.5h.5c.1 0 .4.1.5.4l.8 1.8c.1.2 0 .4-.1.6l-.4.5c-.1.1-.2.2-.1.4.2.4.8 1.3 1.8 1.8.2.1.3 0 .4-.1l.5-.6c.2-.2.4-.2.6-.1l1.7.8c.3.1.4.4.4.5v.5c0 .3-.2.5-.4.6-.5.2-1.1.4-1.8.2-1-.3-2.1-.9-3.1-1.9-1-1-1.6-2.1-1.9-3.1-.2-.8 0-1.4.2-1.8Z" />
                    </svg>
                  </a>

                  <a
                    href="#"
                    class="group inline-flex h-16 w-16 items-center justify-center rounded-[18px] border border-white/10 bg-white/10 text-white backdrop-blur-sm transition hover:bg-white/15 sm:h-[72px] sm:w-[72px] lg:h-[92px] lg:w-[92px] lg:rounded-[22px]"
                    aria-label="Telegram"
                    @click.prevent
                  >
                    <svg viewBox="0 0 24 24" class="h-7 w-7 lg:h-9 lg:w-9" fill="currentColor">
                      <path d="M20.8 4.6c.4-.2.8.2.7.6l-2.8 13c-.1.5-.7.7-1.1.5l-4.1-3-2.1 2c-.2.2-.4.3-.7.3l.4-4.3 7.8-7.1-9.7 6.1-3.9-1.2c-.6-.2-.6-1 .1-1.3l15.4-5.6Z" />
                    </svg>
                  </a>
                </div>
              </div>
            </div>
          </div>
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
                  Оставить заявку
                </h3>
                <p class="mt-2 text-sm text-[#BDC1E2] sm:text-base">
                  Мы свяжемся с вами и подберём оптимальный формат внедрения.
                </p>
              </div>

              <button
                type="button"
                class="inline-flex h-10 w-10 shrink-0 items-center justify-center rounded-full border border-white/10 bg-white/5 text-white transition hover:bg-white/10"
                aria-label="Закрыть форму"
                @click="closeForm"
              >
                <svg viewBox="0 0 20 20" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.8">
                  <path d="M5 5l10 10M15 5 5 15" stroke-linecap="round" />
                </svg>
              </button>
            </div>

            <form class="space-y-4 px-5 py-5 sm:px-7 sm:py-6" @submit.prevent="submitForm">
              <label class="block">
                <span class="mb-2 block text-sm font-medium text-[#E5E7FF]">Имя</span>
                <input
                  v-model.trim="form.name"
                  type="text"
                  class="w-full rounded-[14px] border border-white/10 bg-white/5 px-4 py-3 text-white outline-none placeholder:text-[#9AA0C8] focus:border-white/25"
                  placeholder="Введите имя"
                  required
                />
              </label>

              <label class="block">
                <span class="mb-2 block text-sm font-medium text-[#E5E7FF]">Телефон / Telegram</span>
                <input
                  v-model.trim="form.contact"
                  type="text"
                  class="w-full rounded-[14px] border border-white/10 bg-white/5 px-4 py-3 text-white outline-none placeholder:text-[#9AA0C8] focus:border-white/25"
                  placeholder="+7 (...) или @username"
                  required
                />
              </label>

              <label class="block">
                <span class="mb-2 block text-sm font-medium text-[#E5E7FF]">Комментарий</span>
                <textarea
                  v-model.trim="form.comment"
                  rows="4"
                  class="w-full resize-none rounded-[14px] border border-white/10 bg-white/5 px-4 py-3 text-white outline-none placeholder:text-[#9AA0C8] focus:border-white/25"
                  placeholder="Кратко опишите задачу"
                ></textarea>
              </label>

              <div class="pt-2">
                <button
                  type="submit"
                  class="inline-flex h-12 w-full items-center justify-center rounded-[14px] border border-white/20 bg-[linear-gradient(90deg,#6F63FF_0%,#8B7FFF_100%)] px-5 text-base font-medium text-white shadow-[0_14px_36px_rgba(92,80,255,0.35)] transition hover:opacity-95"
                >
                  Отправить заявку
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

const CONTACT_FORM_OPEN_EVENT = 'contact-feedback-form:open'
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
  }
  if (!opened) {
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

<template>
  <section
    id="contacts"
    class="relative scroll-mt-[92px] overflow-hidden bg-[#01020a] pt-4 pb-0 sm:pt-5 sm:pb-0 lg:scroll-mt-[104px] lg:pt-6 lg:pb-0"
  >
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
      <div class="relative min-h-[420px] overflow-hidden rounded-[36px] bg-[rgba(9,12,41,0.18)] xl:min-h-[560px]">
        <div
          class="relative z-10 grid items-start gap-8 p-6 pb-0 sm:p-10 sm:pb-0 lg:min-h-0 lg:grid-cols-1 lg:items-start lg:px-10 lg:pt-12 lg:pb-0 xl:min-h-[560px] xl:grid-cols-[minmax(0,1fr)_760px] xl:items-stretch xl:px-20 xl:pt-20 xl:pb-0"
        >
          <!-- ЛЕВЫЙ БЛОК -->
          <div class="pt-2 lg:self-start lg:pt-4 xl:pt-14">
            <h2
              class="max-w-[820px] text-[34px] font-semibold leading-[0.96] tracking-[-0.035em] text-white sm:text-[48px] lg:text-[56px] xl:text-[68px]"
            >
              Готовы увеличить эффективность
              <span
                class="block bg-[linear-gradient(90deg,#7A6EFF_0%,#9D96FF_100%)] bg-clip-text text-transparent"
              >
                и опередить конкурентов?
              </span>
              <span class="block">Свяжитесь с нами</span>
            </h2>

            <p
              class="mt-6 max-w-[620px] text-[15px] leading-[1.45] tracking-[-0.02em] text-[#ECEAFF] sm:text-[18px] lg:text-[20px] xl:mt-8 xl:text-[22px]"
            >
              Напишите нам в WhatsApp или Telegram — быстро ответим, уточним задачу и предложим лучший вариант внедрения.
            </p>
          </div>

          <!-- ПРАВЫЙ БЛОК (ВМЕСТО КНОПКИ — КАНАЛЫ СВЯЗИ) -->
          <div class="lg:flex lg:h-full lg:items-end lg:justify-start xl:justify-end">
            <div
              class="relative w-full max-w-full overflow-hidden rounded-[32px] shadow-[0_30px_80px_rgba(34,24,89,0.38)] lg:max-w-[760px] xl:w-[760px]"
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

              <div class="relative z-10 px-6 py-7 sm:px-8 sm:py-8 lg:px-10 lg:py-12 xl:px-14 xl:py-16">
                <h3
                  class="max-w-[560px] text-[26px] font-semibold leading-[1.1] tracking-[-0.03em] text-white sm:text-[32px] lg:text-[38px] xl:text-[44px]"
                >
                  Выберите удобный
                  <span class="block">канал связи</span>
                </h3>

                <p
                  class="mt-5 max-w-[560px] text-[14px] leading-[1.45] tracking-[-0.02em] text-[#ECEAFF] sm:text-[16px] lg:text-[18px] xl:mt-6 xl:text-[20px]"
                >
                  Открываем чат в один клик — без форм и ожиданий.
                </p>

                <div class="mt-8 grid gap-3 sm:gap-4 lg:mt-10 sm:grid-cols-2">
                  <!-- WhatsApp -->
                  <a
                    :href="whatsappHref"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="group inline-flex h-16 w-full items-center justify-center gap-3 rounded-[20px]
                           border border-white/12 bg-white/10 px-6 text-[16px] font-medium tracking-[-0.02em] text-white
                           backdrop-blur-md shadow-[0_16px_40px_rgba(11,12,19,0.30)] transition
                           hover:bg-white/15 active:scale-[0.99]
                           sm:h-[72px] lg:h-[82px] lg:rounded-[22px] lg:text-[18px] xl:h-[92px] xl:rounded-[24px] xl:text-[20px]"
                    aria-label="Написать в WhatsApp"
                  >
                    <span
                      class="inline-flex h-11 w-11 items-center justify-center rounded-[16px] border border-white/12 bg-[#1E2030]/55 transition group-hover:bg-[#1E2030]/70 sm:h-12 sm:w-12"
                      aria-hidden="true"
                    >
                      <!-- WhatsApp icon -->
                      <svg viewBox="0 0 24 24" class="h-6 w-6" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M20 11.5A8 8 0 0 1 8.6 18.7L4.5 20l1.4-3.9A8 8 0 1 1 20 11.5Z" />
                        <path d="M9.2 9.1c.2-.5.4-.5.7-.5h.5c.1 0 .4.1.5.4l.8 1.8c.1.2 0 .4-.1.6l-.4.5c-.1.1-.2.2-.1.4.2.4.8 1.3 1.8 1.8.2.1.3 0 .4-.1l.5-.6c.2-.2.4-.2.6-.1l1.7.8c.3.1.4.4.4.5v.5c0 .3-.2.5-.4.6-.5.2-1.1.4-1.8.2-1-.3-2.1-.9-3.1-1.9-1-1-1.6-2.1-1.9-3.1-.2-.8 0-1.4.2-1.8Z" />
                      </svg>
                    </span>
                    <span>WhatsApp</span>
                  </a>

                  <!-- Telegram -->
                  <a
                    :href="telegramHref"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="group inline-flex h-16 w-full items-center justify-center gap-3 rounded-[20px]
                           border border-white/12 bg-white/10 text-[16px] font-medium tracking-[-0.02em] text-white
                           backdrop-blur-md shadow-[0_16px_40px_rgba(11,12,19,0.30)] transition
                           hover:bg-white/15 active:scale-[0.99]
                           sm:h-[72px] lg:h-[82px] lg:rounded-[22px] lg:text-[18px] xl:h-[92px] xl:rounded-[24px] xl:text-[20px]"
                    aria-label="Написать в Telegram"
                  >
                    <span
                      class="inline-flex h-11 w-11 items-center justify-center rounded-[16px] border border-white/12 bg-[#1E2030]/55 transition group-hover:bg-[#1E2030]/70 sm:h-12 sm:w-12"
                      aria-hidden="true"
                    >
                      <!-- Telegram icon -->
                      <svg viewBox="0 0 24 24" class="h-6 w-6" fill="currentColor">
                        <path d="M20.8 4.6c.4-.2.8.2.7.6l-2.8 13c-.1.5-.7.7-1.1.5l-4.1-3-2.1 2c-.2.2-.4.3-.7.3l.4-4.3 7.8-7.1-9.7 6.1-3.9-1.2c-.6-.2-.6-1 .1-1.3l15.4-5.6Z" />
                      </svg>
                    </span>
                    <span>Telegram</span>
                  </a>
                </div>

                <p class="mt-6 text-xs text-white/70 sm:text-sm">
                  Отвечаем обычно в течение 5–15 минут в рабочее время.
                </p>
              </div>
            </div>
          </div>
          <!-- /ПРАВЫЙ БЛОК -->
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
                class="inline-flex h-10 w-10 shrink-0 items-center justify-center rounded-full border border-white/10 bg-white/5 text-white transition hover:bg-white/10 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-white/60"
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
                  class="w-full rounded-[14px] border border-white/10 bg-white/5 px-4 py-3 text-white outline-none placeholder:text-[#9AA0C8] focus:border-white/25 focus-visible:ring-2 focus-visible:ring-white/15"
                  placeholder="Введите имя"
                  required
                />
              </label>

              <label class="block">
                <span class="mb-2 block text-sm font-medium text-[#E5E7FF]">Телефон / Email</span>
                <input
                  v-model.trim="form.contact"
                  type="text"
                  class="w-full rounded-[14px] border border-white/10 bg-white/5 px-4 py-3 text-white outline-none placeholder:text-[#9AA0C8] focus:border-white/25 focus-visible:ring-2 focus-visible:ring-white/15"
                  placeholder="+7 (...) или email"
                  required
                />
              </label>

              <label class="block">
                <span class="mb-2 block text-sm font-medium text-[#E5E7FF]">Комментарий</span>
                <textarea
                  v-model.trim="form.comment"
                  rows="4"
                  class="w-full resize-none rounded-[14px] border border-white/10 bg-white/5 px-4 py-3 text-white outline-none placeholder:text-[#9AA0C8] focus:border-white/25 focus-visible:ring-2 focus-visible:ring-white/15"
                  placeholder="Кратко опишите задачу"
                ></textarea>
              </label>

              <div class="pt-2">
                <button
                  type="submit"
                  class="inline-flex h-12 w-full items-center justify-center rounded-[14px] border border-white/20 bg-[linear-gradient(90deg,#6F63FF_0%,#8B7FFF_100%)] px-5 text-base font-medium text-white shadow-[0_14px_36px_rgba(92,80,255,0.35)] transition hover:opacity-95 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-white/40"
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
import { computed, onBeforeUnmount, onMounted, ref, watch } from 'vue'

const CONTACT_FORM_OPEN_EVENT = 'contact-feedback-form:open'

// ВАЖНО: вставь сюда свои реальные контакты.
// Сейчас стоят безопасные заглушки, чтобы ничего случайно не "утекло" в прод.
const WHATSAPP_PHONE_E164 = '' // пример: '79991234567' (без +)
const WHATSAPP_TEXT = 'Здравствуйте! Хочу увеличить эффективность продаж с помощью AI. Подскажите, что нужно для старта?'
const TELEGRAM_USERNAME = '' // пример: 'moonai_support' (без @)

const whatsappHref = computed(() => {
  if (!WHATSAPP_PHONE_E164) return '#'
  const text = encodeURIComponent(WHATSAPP_TEXT)
  return `https://wa.me/${WHATSAPP_PHONE_E164}?text=${text}`
})

const telegramHref = computed(() => {
  if (!TELEGRAM_USERNAME) return '#'
  return `https://t.me/${TELEGRAM_USERNAME}`
})

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

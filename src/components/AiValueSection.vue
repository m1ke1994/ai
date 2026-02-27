<script setup>
const CONTACT_FORM_OPEN_EVENT = 'contact-feedback-form:open'

const openContactFormModal = () => {
  if (typeof window === 'undefined') return
  window.dispatchEvent(new Event(CONTACT_FORM_OPEN_EVENT))
}

const valuePoints = [
  'Бесплатное обучение AI-продавца на ваших данных',
  'Настройка и интеграция всех каналов и сервисов',
  'Тестовый период 7 дней (без рисков)',
  'Безлимитное количество диалогов',
  'Донастройка и сопровождение на всём периоде использования',
  'Платите только за ежемесячную подписку',
  'Подключаете только если довольны результатом теста',
  'AI увеличивает прибыль и снижает расходы',
]

const contactChannels = [
  'Сайт',
  'Telegram',
  'Avito',
  'Instagram',
  'Facebook',
  'WhatsApp',
  'YouTube',
  'TikTok',
  'Mail',
  'ВКонтакте',
  'Max',
]

const integrations = [
  'Товарные фиды: AI знает остатки по товарам на складе',
  'Пользовательские вебхуки и API-интеграции (подключение любых систем)',
  'Slack (уведомления, управление беседами, совместная работа)',
  'Google Analytics и Яндекс Метрика/Аналитика',
]
</script>

<template>
  <section
    id="ai-value"
    class="relative isolate scroll-mt-[92px] rounded-none bg-[#F3F4F7] py-14 lg:scroll-mt-[104px] sm:py-20 lg:py-28"
  >
    <div
      aria-hidden="true"
      class="pointer-events-none absolute inset-0 opacity-100"
      style="
        background:
          radial-gradient(36rem 18rem at 10% 0%, rgba(111, 99, 255, 0.10), transparent 72%),
          radial-gradient(34rem 18rem at 92% 12%, rgba(126, 182, 255, 0.10), transparent 72%),
          radial-gradient(30rem 16rem at 50% 100%, rgba(111, 99, 255, 0.05), transparent 78%);
      "
    />

    <div class="relative z-10 mx-auto w-full max-w-[1760px] px-4 sm:px-6 lg:px-10">
      <!-- Title -->
      <div class="text-center">
        <h2
          class="text-[34px] font-semibold leading-[1.06] tracking-[-0.03em] text-[#111218] sm:text-[44px] lg:text-[66px] lg:leading-[1.04]"
        >
          AI — не статья расходов
        </h2>
        <h3
          class="mt-2 text-[30px] font-semibold leading-[1.06] tracking-[-0.03em] text-[#9EA4B8] sm:text-[40px] lg:mt-3 lg:text-[58px] lg:leading-[1.04]"
        >
          а
          <span class="bg-[linear-gradient(90deg,#5E52DE_0%,#8075FF_55%,#6FA9FF_100%)] bg-clip-text text-transparent">
            источник дохода
          </span>
        </h3>
      </div>

      <!-- ✅ Вертикальный стек: 1) запуск, 2) интеграции, 3) каналы -->
      <div class="mt-8 grid grid-cols-1 gap-5 sm:mt-10 lg:gap-6">
        <!-- 1) Запускаем AI-продавца -->
        <div
          class="relative overflow-hidden rounded-[30px] border border-[#DADFF3] bg-[linear-gradient(145deg,rgba(111,99,255,0.10)_0%,rgba(255,255,255,0.95)_35%,rgba(111,99,255,0.04)_100%)] p-5 shadow-[0_24px_70px_rgba(38,44,88,0.10)] sm:rounded-[32px] sm:p-6 lg:p-7"
        >
          <div
            aria-hidden="true"
            class="pointer-events-none absolute inset-0 opacity-[0.25]"
            style="
              background-image: repeating-linear-gradient(
                130deg,
                rgba(111, 99, 255, 0.14) 0px,
                rgba(111, 99, 255, 0.14) 1px,
                transparent 1px,
                transparent 14px
              );
            "
          />
          <div
            aria-hidden="true"
            class="pointer-events-none absolute -left-16 -top-16 h-40 w-40 rounded-full bg-[rgba(111,99,255,0.14)] blur-3xl"
          />
          <div
            aria-hidden="true"
            class="pointer-events-none absolute -bottom-12 right-0 h-36 w-36 rounded-full bg-[rgba(126,182,255,0.16)] blur-3xl"
          />

          <div class="relative">
            <div class="flex flex-wrap items-center gap-2.5">
              <span
                class="inline-flex items-center rounded-full border border-[#CFC8FF] bg-[rgba(111,99,255,0.08)] px-3 py-1.5 text-[11px] font-semibold tracking-[0.04em] text-[#5B50CF]"
              >
                7 дней теста
              </span>
              <span
                class="inline-flex items-center rounded-full border border-[#E3E7F4] bg-white/80 px-3 py-1.5 text-[11px] font-medium tracking-[-0.01em] text-[#5B627E]"
              >
                Без риска для бизнеса
              </span>
            </div>

            <h4 class="mt-4 text-[22px] font-semibold leading-[1.08] tracking-[-0.03em] text-[#141633] sm:text-[26px] lg:text-[30px]">
              Запускаем AI-продавца как рабочий канал продаж, а не как эксперимент
            </h4>

            <p class="mt-3 max-w-[980px] text-[14px] leading-[1.5] tracking-[-0.01em] text-[#646C89] sm:text-[15px] lg:text-[16px]">
              Вы получаете обучение, интеграции, поддержку и тестовый период до оплаты. Решение должно показать ценность в бизнесе, а не просто красиво выглядеть.
            </p>

            <div class="mt-5 grid gap-3 sm:grid-cols-2 lg:grid-cols-3">
              <div
                v-for="point in valuePoints"
                :key="point"
                class="flex items-start gap-2.5 rounded-[18px] border border-white/50 bg-white/70 px-3.5 py-3 shadow-[0_14px_36px_rgba(18,26,52,0.05)] backdrop-blur-sm"
              >
                <span
                  aria-hidden="true"
                  class="mt-0.5 grid h-6 w-6 shrink-0 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_22px_rgba(89,75,255,0.24)]"
                >
                  <svg viewBox="0 0 16 16" class="h-3.5 w-3.5 text-white" fill="none">
                    <path d="M4 8.2l2.1 2.1L12 4.7" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
                  </svg>
                </span>
                <span class="text-[13px] leading-[1.38] tracking-[-0.01em] text-[#20253A] sm:text-[14px]">
                  {{ point }}
                </span>
              </div>
            </div>

      
          </div>
        </div>

        <!-- 2) Интеграции и аналитика -->
        <div
          class="relative overflow-hidden rounded-[30px] border border-[#E1E5F2] bg-[linear-gradient(180deg,rgba(255,255,255,0.92)_0%,rgba(247,248,252,0.95)_100%)] p-5 shadow-[0_18px_54px_rgba(18,26,52,0.07)] sm:rounded-[32px] sm:p-6"
        >
          <div aria-hidden="true" class="pointer-events-none absolute -right-10 top-0 h-28 w-28 rounded-full bg-[rgba(111,99,255,0.10)] blur-2xl" />
          <div aria-hidden="true" class="pointer-events-none absolute -left-10 bottom-0 h-28 w-28 rounded-full bg-[rgba(126,182,255,0.12)] blur-2xl" />

          <div class="relative">
            <div class="inline-flex items-center gap-2 rounded-full border border-[#E3E8F6] bg-white/85 px-3 py-1.5 text-[11px] font-medium tracking-[-0.01em] text-[#59607D]">
              <span class="h-2 w-2 rounded-full bg-[#7BB3FF]" aria-hidden="true" />
              Интеграции и аналитика
            </div>

            <h4 class="mt-4 text-[20px] font-semibold tracking-[-0.03em] text-[#141633] sm:text-[22px]">
              Подключаем данные, каналы и контроль эффективности
            </h4>

            <ul class="mt-4 space-y-2.5">
              <li
                v-for="item in integrations"
                :key="item"
                class="flex items-start gap-2.5 rounded-[16px] border border-[#E8ECF6] bg-white/80 px-3.5 py-3 text-[13px] leading-[1.42] tracking-[-0.01em] text-[#2C3148] shadow-[0_10px_24px_rgba(18,26,52,0.03)] sm:text-[14px]"
              >
                <span
                  aria-hidden="true"
                  class="mt-0.5 inline-flex h-5 w-5 shrink-0 items-center justify-center rounded-full border border-[#DDE2F2] bg-[#F8F9FF] text-[#6A5EFD]"
                >
                  <svg viewBox="0 0 16 16" class="h-3 w-3" fill="none">
                    <path d="M4 8.2l2.1 2.1L12 4.7" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
                  </svg>
                </span>
                <span>{{ item }}</span>
              </li>
            </ul>
          </div>
        </div>

        <!-- 3) Каналы контакта -->
        <div
          class="relative overflow-hidden rounded-[30px] border border-[#E1E5F2] bg-white/75 p-5 shadow-[0_18px_54px_rgba(18,26,52,0.07)] backdrop-blur-sm sm:rounded-[32px] sm:p-6"
        >
          <div
            aria-hidden="true"
            class="pointer-events-none absolute inset-0 opacity-[0.20]"
            style="
              background-image: repeating-linear-gradient(
                125deg,
                rgba(126, 182, 255, 0.14) 0px,
                rgba(126, 182, 255, 0.14) 1px,
                transparent 1px,
                transparent 15px
              );
            "
          />

          <div class="relative">
            <div class="inline-flex items-center gap-2 rounded-full border border-[#E3E8F6] bg-white/85 px-3 py-1.5 text-[11px] font-medium tracking-[-0.01em] text-[#59607D]">
              <span class="h-2 w-2 rounded-full bg-[#6F63FF]" aria-hidden="true" />
              Омниканальность
            </div>
            <h4 class="mt-4 text-[20px] font-semibold tracking-[-0.03em] text-[#141633] sm:text-[22px]">
              Каналы контакта
            </h4>
            <p class="mt-2 text-[13px] leading-[1.45] text-[#6A718C] sm:text-[14px]">
              Единая логика ответов и сбор лидов во всех ключевых каналах общения с клиентом.
            </p>

            <div class="mt-4 grid grid-cols-2 gap-2.5 sm:grid-cols-3 lg:grid-cols-4">
              <div
                v-for="channel in contactChannels"
                :key="channel"
                class="group inline-flex min-h-[42px] items-center gap-2 rounded-[14px] border border-[#E5E9F5] bg-white/80 px-3 py-2 text-[12px] font-medium tracking-[-0.01em] text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.03)] transition hover:-translate-y-0.5 hover:border-[#D3DAEF] hover:shadow-[0_14px_28px_rgba(18,26,52,0.06)]"
              >
                <span
                  aria-hidden="true"
                  class="grid h-5 w-5 shrink-0 place-items-center rounded-full border border-[#DCE1F2] bg-white text-[#6A5EFD] transition group-hover:border-[#CDC5FF] group-hover:bg-[rgba(111,99,255,0.06)]"
                >
                  <svg viewBox="0 0 16 16" class="h-3 w-3" fill="none">
                    <path
                      d="M8 2.7a5.3 5.3 0 1 0 0 10.6A5.3 5.3 0 0 0 8 2.7Zm0 0v10.6M2.7 8h10.6"
                      stroke="currentColor"
                      stroke-width="1.25"
                      stroke-linecap="round"
                    />
                  </svg>
                </span>
                <span class="truncate">{{ channel }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- /stack -->
    </div>
  </section>
</template>
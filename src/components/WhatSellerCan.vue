<script setup>
import { nextTick, ref } from 'vue'

const stats = [
  { value: '0 тг', text: 'за установку ИИ' },
  { value: '100%', text: 'верификация от meta, google,\namocrm, bitrix и другие' },
  { value: '24/7', text: 'поддержка от проектных\nменеджеров' },
]

const compareRows = [
  {
    label: 'Консультация',
    ai: 'Обучен на всей базе знаний компании и отвечает точно по любому товару или услуге с первой минуты.',
    human: 'Знает только основные позиции и отвечает в рамках своего опыта.',
  },
  {
    label: 'Прогрев клиента',
    ai: 'Системно выявляет потребность, после ответа всегда задаёт вопрос и подводит к целевому действию. Готов бесконечно разговаривать с клиентом.',
    human: 'Ведёт диалог по скрипту и зависит от настроения и загрузки. Выдыхается после 10 диалогов.',
  },
  {
    label: 'Дожим и возражения',
    ai: 'Дожимает до сделки: не «ну-у-у…», не «давайте потом». Обучен практикам продаж и найдёт 1001 способ обойти возражение.',
    human: 'Дожимает по настроению: спорит, давит, «выдыхается», уводит в «хорошо, давайте позже» и переносит.',
  },
  {
    label: 'Доппродажа',
    ai: 'Автоматически предлагает сопутствующие товары и увеличивает средний чек.',
    human: 'Предлагает дополнительные товары, если вспомнит.',
  },
  {
    label: 'Скорость ответа',
    ai: 'Отвечает за 1–5 секунд, 24/7.',
    human: 'Отвечает, когда освободится.',
  },
  {
    label: 'Одновременные диалоги',
    ai: 'Тысячи диалогов одновременно без потери качества.',
    human: '1–3 активных клиента одновременно.',
  },
  {
    label: 'Знание языков',
    ai: 'Тысячи языков — на каком пишет клиент, на таком и отвечает.',
    human: '1–3 языка максимум.',
  },
  {
    label: 'Этапы сделки',
    ai: 'Передаёт горячего клиента вашему менеджеру для закрытия сделки, поднимая мотивацию.',
    human: 'Устаёт от квалификации, тратит энергию на прогрев, не остаётся сил на дожим и закрытие сделки.',
  },
]

// ✅ Summary (премиальная сводка)
const aiSummary = [
  'Отвечает за 1–5 секунд 24/7 без перерывов и выходных',
  'Масштабируется на тысячи диалогов одновременно без потери качества',
  'Ведёт клиента по воронке: выявляет потребность и подводит к целевому действию',
  'Дожимает и отрабатывает возражения — без усталости и «давайте потом»',
  'Автоматически допродаёт и увеличивает средний чек',
  'Знает продукт: обучается на базе знаний, скриптах, диалогах, FAQ',
  'Говорит на языке клиента (много языков) и соблюдает терминологию компании',
  'Передаёт «горячих» лидов менеджеру на закрытие сделки',
]

const humanLimits = [
  'Ограничен временем: не 24/7, отвечает с задержкой',
  'Быстро выдыхается при потоке — падает качество',
  'Чаще действует по скрипту и настроению, зависит от загрузки',
  'Не держит в голове весь ассортимент и нюансы продукта',
]

const isCompareOpen = ref(false)
const compareDetailsRef = ref(null)

const scrollToExpandedCompare = () => {
  if (typeof window === 'undefined') return
  const element = compareDetailsRef.value
  if (!element) return

  window.requestAnimationFrame(() => {
    window.requestAnimationFrame(() => {
      element.scrollIntoView({
        behavior: 'smooth',
        block: 'start',
      })
    })
  })
}

const toggleCompare = async () => {
  const nextState = !isCompareOpen.value
  isCompareOpen.value = nextState

  if (!nextState) return

  await nextTick()
  scrollToExpandedCompare()
}
</script>

<template>
  <section
    id="advantages"
    class="relative z-10 scroll-mt-[92px] bg-[#F3F4F7] pt-0 pb-5 lg:scroll-mt-[104px] lg:pb-6"
  >
    <div class="overflow-x-hidden">
      <div class="mx-auto w-full max-w-[1880px] px-4 sm:px-6 lg:px-10">
        <div class="relative overflow-hidden bg-white">
         
          <!-- ✅ Блок с описанием обучения AI (оставляем) -->
<!-- ✅ Блок с описанием обучения AI (оставляем) -->
  <div class="px-4 pb-8 pt-6 sm:px-6 lg:px-10 lg:pb-12 lg:pt-10">
    <div
      class="relative overflow-hidden rounded-[20px] border border-[#E8EBF4] bg-[linear-gradient(180deg,#FFFFFF_0%,#F7F8FC_100%)] p-4 shadow-[0_18px_60px_rgba(20,27,58,0.06)] sm:rounded-[24px] sm:p-6 lg:rounded-[28px] lg:p-8"
    >
      <div
        class="pointer-events-none absolute inset-0 opacity-80"
        style="
          background:
            radial-gradient(34rem 18rem at 8% 10%, rgba(75, 57, 255, 0.08), transparent 72%),
            radial-gradient(30rem 18rem at 92% 88%, rgba(125, 108, 255, 0.08), transparent 72%);
        "
        aria-hidden="true"
      />

      <div
        class="relative grid gap-5 lg:grid-cols-[minmax(0,1.08fr)_minmax(0,0.92fr)] lg:items-start lg:gap-6"
      >
        <!-- LEFT -->
        <div class="text-left">
          <div
            class="inline-flex items-center gap-2 rounded-full border border-[#E3E7F2] bg-white/90 px-2.5 py-2 shadow-[0_10px_24px_rgba(18,26,52,0.05)] backdrop-blur"
          >
            <span
              class="grid h-6 w-6 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_8px_20px_rgba(89,75,255,0.35)]"
            >
              <img
                src="/vecor.svg"
                alt=""
                class="h-3.5 w-3.5 brightness-[5] saturate-0"
                aria-hidden="true"
              />
            </span>
            <span class="text-[12px] font-medium tracking-[-0.01em] text-[#2F3452] sm:text-[20px]">
              Обучение AI на ваших данных
            </span>
          </div>

          <!-- ✅ Сетка: по 2 в ряд, центрируем содержимое каждой плашки -->
          <div class="mt-4 space-y-2.5">
            <!-- Row 1 -->
            <div class="grid grid-cols-2 gap-2.5">
              <div
                class="flex w-full items-center justify-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[18px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]"
              >
                <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                <span>Сайт</span>
              </div>
              <div
                class="flex w-full items-center justify-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[18px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]"
              >
                <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                <span>Прайс-листы</span>
              </div>
            </div>

            <!-- Row 2 -->
            <div class="grid grid-cols-2 gap-2.5">
              <div
                class="flex w-full items-center justify-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[18px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]"
              >
                <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                <span>Товары и услуги</span>
              </div>
              <div
                class="flex w-full items-center justify-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[18px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]"
              >
                <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                <span>Лучшие диалоги</span>
              </div>
            </div>

            <!-- Row 3 -->
            <div class="grid grid-cols-2 gap-2.5">
              <div
                class="flex w-full items-center justify-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[18px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]"
              >
                <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                <span>Скрипты</span>
              </div>
              <div
                class="flex w-full items-center justify-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[18px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]"
              >
                <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                <span>FAQ</span>
              </div>
            </div>

            <!-- Row 4 (last: single item + пустышка для сетки) -->
            <div class="grid grid-cols-2 gap-2.5">
              <div
                class="flex w-full items-center justify-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[18px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]"
              >
                <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                <span>Товарные фиды</span>
              </div>
              <div aria-hidden="true"></div>
            </div>
          </div>
        </div>

        <!-- RIGHT -->
        <div
          class="relative overflow-hidden rounded-[18px] border border-[#D9DEF0] bg-[#5b6098] p-4 shadow-[0_24px_60px_rgba(18,26,52,0.18)] sm:rounded-[20px] sm:p-5 lg:p-6 text-white"
        >
          <div
            class="pointer-events-none absolute -right-14 -top-14 h-32 w-32 rounded-full bg-[#171B42]/20 blur-3xl"
            aria-hidden="true"
          />
          <div
            class="pointer-events-none absolute -bottom-10 -left-10 h-28 w-28 rounded-full bg-[#171B42]/10 blur-3xl"
            aria-hidden="true"
          />

          <div class="relative">
            <div
              class="inline-flex items-center gap-2 rounded-full border border-white/10 bg-white/5 px-3 py-1.5 text-[11px] font-medium text-white sm:text-[12px]"
            >
              <span class="h-2 w-2 rounded-full bg-[#78F7C7] shadow-[0_0_14px_rgba(120,247,199,0.8)]" />
              С первой минуты готов к работе
            </div>

            <p
              class="mt-3 text-[15px] font-medium leading-[1.38] tracking-[-0.01em] text-white sm:text-[16px] lg:text-[19px]"
            >
              AI-продажник с первой минуты работы знает про вашу компанию и продукт больше и лучше
              любого вашего самого опытного менеджера.
            </p>

            <div class="mt-4 grid gap-2.5 sm:gap-3">
              <div class="flex items-start gap-2.5 text-[12px] leading-[1.35] text-white sm:text-[13px]">
                <img
                  src="/vecor.svg"
                  alt=""
                  class="mt-0.5 h-3.5 w-3.5 shrink-0 brightness-[4] saturate-0"
                  aria-hidden="true"
                />
                <span class="text-white">Отвечает по вашей продуктовой логике и терминологии</span>
              </div>

              <div class="flex items-start gap-2.5 text-[12px] leading-[1.35] text-white sm:text-[13px]">
                <img
                  src="/vecor.svg"
                  alt=""
                  class="mt-0.5 h-3.5 w-3.5 shrink-0 brightness-[4] saturate-0"
                  aria-hidden="true"
                />
                <span class="text-white">Использует знания из лучших диалогов и скриптов продаж</span>
              </div>

              <div class="flex items-start gap-2.5 text-[12px] leading-[1.35] text-white sm:text-[13px]">
                <img
                  src="/vecor.svg"
                  alt=""
                  class="mt-0.5 h-3.5 w-3.5 shrink-0 brightness-[4] saturate-0"
                  aria-hidden="true"
                />
                <span class="text-white">Работает с актуальными данными компании и ассортимента</span>
              </div>
            </div>
          </div>
        </div>
        <!-- /RIGHT -->
      </div>
    </div>
  </div>

          <!-- ✅ NEW (вариант 4): Summary + раскрытие деталей -->
         
    <div
      class="summary-shell relative overflow-hidden rounded-[26px] border border-[#E6EAF4] bg-[linear-gradient(180deg,#FFFFFF_0%,#F7F8FC_100%)] shadow-[0_30px_90px_rgba(18,26,52,0.12)]"
    >
      <!-- lights -->
      <div
        class="pointer-events-none absolute inset-0 opacity-100"
        style="
          background:
            radial-gradient(42rem 18rem at 12% 0%, rgba(75, 57, 255, 0.11), transparent 62%),
            radial-gradient(36rem 22rem at 100% 70%, rgba(125, 108, 255, 0.10), transparent 64%),
            linear-gradient(180deg, rgba(255,255,255,0.85), rgba(255,255,255,0.0));
        "
        aria-hidden="true"
      />
      <div
        class="pointer-events-none absolute -top-24 left-1/2 h-56 w-[560px] -translate-x-1/2 rounded-full bg-[linear-gradient(90deg,rgba(75,57,255,0.18),rgba(138,125,255,0.10))] blur-3xl"
        aria-hidden="true"
      />

      <div class="relative p-5 sm:p-6 lg:p-8">
        <!-- header row (без кнопки) -->
        <div class="flex flex-col gap-2">
          <div class="text-[14px] font-semibold tracking-[-0.01em] text-[#2F3452] lg:text-[15px]">
            Сводка возможностей
          </div>
          <div
            class="max-w-[980px] text-[16px] font-semibold leading-[1.18] tracking-[-0.03em] text-[#141633] sm:text-[20px] lg:text-[26px]"
          >
            Эффективные растут не эффективные исчезают

          </div>
        </div>

        <!-- ✅ ОСТАВЛЯЕМ ТОЛЬКО ТО, ЧТО БЫЛО В РАСКРЫВАЮЩЕМСЯ БЛОКЕ -->
        <div
          class="mt-6 overflow-hidden rounded-[22px] border border-[#E6EAF4] bg-white/60 shadow-[0_22px_70px_rgba(18,26,52,0.08)] scroll-mt-[110px]"
        >
          <!-- desktop compare -->
          <div class="hidden lg:block">
            <div class="grid grid-cols-[minmax(240px,0.30fr)_minmax(0,0.35fr)_minmax(0,0.35fr)] px-6 pt-6">
              <div class="text-[14px] font-semibold tracking-[-0.01em] text-[#2F3452]">Этап</div>
              <div class="text-[14px] font-semibold tracking-[-0.01em] text-[#4B39FF]">AI-отдел продаж</div>
              <div class="text-[14px] font-semibold tracking-[-0.01em] text-[#2F3452]">Менеджер</div>
            </div>

            <div class="mt-4 divide-y divide-[#E8EBF4]">
              <div
                v-for="(r, i) in compareRows"
                :key="i"
                class="grid grid-cols-[minmax(240px,0.30fr)_minmax(0,0.35fr)_minmax(0,0.35fr)] px-6 py-6"
              >
                <div>
                  <div class="text-[16px] font-semibold tracking-[-0.02em] text-[#141633]">
                    {{ r.label }}
                  </div>
                  <div class="mt-1 text-[13px] leading-[1.35] text-[#7A809A]">Сравнение по этапу</div>
                </div>

                <div>
                  <div
                    class="rounded-[18px] border border-white/40 bg-[linear-gradient(135deg,rgba(75,57,255,0.10)_0%,rgba(138,125,255,0.06)_100%)] p-5 shadow-[0_18px_55px_rgba(89,75,255,0.12)]"
                  >
                    <div class="flex items-start gap-3">
                      <span
                        class="mt-0.5 grid h-7 w-7 shrink-0 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_22px_rgba(89,75,255,0.24)]"
                        aria-hidden="true"
                      >
                        <span class="text-[14px] text-white">✓</span>
                      </span>
                      <div class="text-[15px] leading-[1.55] tracking-[-0.01em] text-[#141633]">
                        {{ r.ai }}
                      </div>
                    </div>
                  </div>
                </div>

                <div>
                  <div class="rounded-[18px] border border-[#E6EAF4] bg-white/85 p-5 shadow-[0_16px_44px_rgba(18,26,52,0.06)]">
                    <div class="flex items-start gap-3">
                      <span class="mt-0.5 grid h-7 w-7 shrink-0 place-items-center rounded-full bg-[#111827]/5" aria-hidden="true">
                        <span class="text-[14px] font-semibold text-[#2F3452]">—</span>
                      </span>
                      <div class="text-[15px] leading-[1.55] tracking-[-0.01em] text-[#2B2E3A]">
                        {{ r.human }}
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <div class="px-6 pb-6 pt-1 text-center text-[13px] leading-[1.45] text-[#6B7190]">
              Детали: почему AI выдерживает поток, а менеджер — нет.
            </div>
          </div>

          <!-- mobile compare -->
          <div class="lg:hidden">
            <div class="px-4 pt-5 sm:px-6">
              <div class="text-[14px] font-semibold tracking-[-0.02em] text-[#141633]">Сравнение по этапам</div>
              <div class="mt-1 text-[13px] leading-[1.45] text-[#616782]">Прокрути — детали ниже.</div>
            </div>

            <div class="mt-4 space-y-4 px-4 pb-6 sm:px-6">
              <div
                v-for="(r, i) in compareRows"
                :key="i"
                class="rounded-[22px] border border-[#E6EAF4] bg-white/80 p-4 shadow-[0_18px_60px_rgba(18,26,52,0.08)]"
              >
                <div class="text-[15px] font-semibold tracking-[-0.02em] text-[#141633]">
                  {{ r.label }}
                </div>

                <div class="mt-3 grid gap-3">
                  <div
                    class="rounded-[18px] border border-white/40 bg-[linear-gradient(135deg,rgba(75,57,255,0.10)_0%,rgba(138,125,255,0.06)_100%)] p-4 shadow-[0_18px_52px_rgba(89,75,255,0.14)]"
                  >
                    <div class="flex items-center gap-2 text-[12px] font-semibold text-[#4B39FF]">
                      <span class="grid h-6 w-6 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] text-white">
                        ✓
                      </span>
                      AI-отдел продаж
                    </div>
                    <div class="mt-2 text-[14px] leading-[1.55] tracking-[-0.01em] text-[#141633]">
                      {{ r.ai }}
                    </div>
                  </div>

                  <div class="rounded-[18px] border border-[#E6EAF4] bg-white/90 p-4 shadow-[0_14px_44px_rgba(18,26,52,0.06)]">
                    <div class="flex items-center gap-2 text-[12px] font-semibold text-[#2F3452]">
                      <span class="grid h-6 w-6 place-items-center rounded-full bg-[#111827]/5 text-[#2F3452]">
                        —
                      </span>
                      Менеджер
                    </div>
                    <div class="mt-2 text-[14px] leading-[1.55] tracking-[-0.01em] text-[#2B2E3A]">
                      {{ r.human }}
                    </div>
                  </div>
                </div>
              </div>

              <div class="pt-1 text-center text-[13px] leading-[1.45] text-[#6B7190]">
                Итог: AI берёт поток, менеджер — закрывает.
              </div>
            </div>
          </div>
        </div>

        <!-- subtle footer line -->
        
      </div>

      <!-- luxury border -->
      <div class="pointer-events-none absolute inset-0 rounded-[26px]" aria-hidden="true">
        <div class="absolute inset-0 rounded-[26px] border border-white/70 opacity-45"></div>
        <div class="absolute inset-[1px] rounded-[25px] border border-[#E6EAF4] opacity-85"></div>
      </div>
    </div>
  </div>
          <!-- /NEW -->
        </div>
      </div>
    
  </section>
</template>

<style scoped>
.summary-shell {
  background-image:
    radial-gradient(1200px 320px at 50% 0%, rgba(75, 57, 255, 0.06), transparent 60%),
    radial-gradient(900px 280px at 85% 70%, rgba(138, 125, 255, 0.06), transparent 62%),
    linear-gradient(180deg, #ffffff 0%, #f7f8fc 100%);
}

.summary-card--ai {
  position: relative;
}
.summary-card--ai::after {
  content: '';
  position: absolute;
  inset: -1px;
  border-radius: 22px;
  background: radial-gradient(560px 200px at 18% 0%, rgba(75, 57, 255, 0.14), transparent 55%);
  pointer-events: none;
  opacity: 0.55;
}
</style>

<script setup>
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
</script>

<template>
  <section
    id="advantages"
    class="relative z-10 scroll-mt-[92px] bg-[#F3F4F7] pt-0 pb-12 lg:scroll-mt-[104px]"
  >
    <div class="overflow-x-hidden">
      <div class="mx-auto w-full max-w-[1880px] px-4 sm:px-6 lg:px-10">
        <div class="relative overflow-hidden rounded-t-[20px] bg-white">
          <!-- ✅ СТАТЫ (верх секции) -->
          <div class="px-4 pt-6 sm:px-6 lg:px-10 lg:pt-8">
            
          </div>

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

              <div class="relative grid gap-5 lg:grid-cols-[minmax(0,1.08fr)_minmax(0,0.92fr)] lg:items-start lg:gap-6">
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
                    <span class="text-[12px] font-medium tracking-[-0.01em] text-[#2F3452] sm:text-[13px]">
                      Обучение AI на ваших данных
                    </span>
                  </div>

                  <p class="mt-4 max-w-[780px] text-[16px] leading-[1.45] tracking-[-0.01em] text-[#2B2E3A] sm:text-[18px] lg:text-[22px]">
                    Обучаем AI на ваших данных: сайт, прайс-листы, описание товаров и услуг, лучшие диалоги,
                    скрипты, FAQ, товарные фиды и другие материалы.
                  </p>

                  <div class="mt-4 flex flex-wrap gap-2.5">
                    <div class="inline-flex items-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[12px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]">
                      <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                      <span>Сайт</span>
                    </div>
                    <div class="inline-flex items-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[12px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]">
                      <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                      <span>Прайс-листы</span>
                    </div>
                    <div class="inline-flex items-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[12px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]">
                      <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                      <span>Товары и услуги</span>
                    </div>
                    <div class="inline-flex items-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[12px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]">
                      <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                      <span>Лучшие диалоги</span>
                    </div>
                    <div class="inline-flex items-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[12px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]">
                      <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                      <span>Скрипты</span>
                    </div>
                    <div class="inline-flex items-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[12px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]">
                      <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                      <span>FAQ</span>
                    </div>
                    <div class="inline-flex items-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[12px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]">
                      <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                      <span>Товарные фиды</span>
                    </div>
                  </div>
                </div>

                <div class="relative overflow-hidden rounded-[18px] border border-[#D9DEF0] bg-[#5b6098] p-4 shadow-[0_24px_60px_rgba(18,26,52,0.18)] sm:rounded-[20px] sm:p-5 lg:p-6">
                  <div class="pointer-events-none absolute -right-14 -top-14 h-32 w-32 rounded-full bg-[#171B42]/20 blur-3xl" aria-hidden="true" />
                  <div class="pointer-events-none absolute -bottom-10 -left-10 h-28 w-28 rounded-full bg-[#171B42]/10 blur-3xl" aria-hidden="true" />

                  <div class="relative">
                    <div class="inline-flex items-center gap-2 rounded-full border border-white/10 bg-white/5 px-3 py-1.5 text-[11px] font-medium text-white/80 sm:text-[12px]">
                      <span class="h-2 w-2 rounded-full bg-[#78F7C7] shadow-[0_0_14px_rgba(120,247,199,0.8)]" />
                      С первой минуты готов к работе
                    </div>

                    <p class="mt-3 text-[15px] font-medium leading-[1.38] tracking-[-0.01em] text-white sm:text-[16px] lg:text-[19px]">
                      AI-продажник с первой минуты работы знает про вашу компанию и продукт больше и лучше
                      любого вашего самого опытного менеджера.
                    </p>

                    <div class="mt-4 grid gap-2.5 sm:gap-3">
                      <div class="flex items-start gap-2.5 text-[12px] leading-[1.35] text-white/78 sm:text-[13px]">
                        <img src="/vecor.svg" alt="" class="mt-0.5 h-3.5 w-3.5 shrink-0 brightness-[4] saturate-0" aria-hidden="true" />
                        <span>Отвечает по вашей продуктовой логике и терминологии</span>
                      </div>
                      <div class="flex items-start gap-2.5 text-[12px] leading-[1.35] text-white/78 sm:text-[13px]">
                        <img src="/vecor.svg" alt="" class="mt-0.5 h-3.5 w-3.5 shrink-0 brightness-[4] saturate-0" aria-hidden="true" />
                        <span>Использует знания из лучших диалогов и скриптов продаж</span>
                      </div>
                      <div class="flex items-start gap-2.5 text-[12px] leading-[1.35] text-white/78 sm:text-[13px]">
                        <img src="/vecor.svg" alt="" class="mt-0.5 h-3.5 w-3.5 shrink-0 brightness-[4] saturate-0" aria-hidden="true" />
                        <span>Работает с актуальными данными компании и ассортимента</span>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- ✅ Заголовок (как было) -->
          <div class="px-4 pb-10 pt-12 text-center sm:px-6 sm:pt-16 lg:px-10 lg:pt-20 lg:pb-10">
            <h2 class="text-[34px] font-semibold leading-[1.06] tracking-[-0.03em] text-[#111218] sm:text-[44px] lg:text-[66px] lg:leading-[1.04]">
              Что умеет
            </h2>
            <p class="mt-2 text-[34px] font-semibold leading-[1.06] tracking-[-0.03em] text-[#9EA4B8] sm:text-[44px] lg:mt-3 lg:text-[66px] lg:leading-[1.04]">
              AI продавец
            </p>
          </div>

          <!-- ✅ NEW: премиальный сравнение-блок -->
          <div class="px-4 pb-12 sm:px-6 lg:px-10 lg:pb-16">
            <div
              class="compare-shell relative overflow-hidden rounded-[24px] border border-[#E6EAF4] bg-[linear-gradient(180deg,#FFFFFF_0%,#F7F8FC_100%)] shadow-[0_30px_90px_rgba(18,26,52,0.12)] sm:rounded-[28px]"
            >
              <!-- премиальные блики -->
              <div
                class="pointer-events-none absolute inset-0 opacity-100"
                style="
                  background:
                    radial-gradient(38rem 18rem at 12% 0%, rgba(75, 57, 255, 0.10), transparent 60%),
                    radial-gradient(34rem 22rem at 100% 80%, rgba(125, 108, 255, 0.10), transparent 62%),
                    linear-gradient(180deg, rgba(255,255,255,0.85), rgba(255,255,255,0.0));
                "
                aria-hidden="true"
              />
              <div
                class="pointer-events-none absolute -top-24 left-1/2 h-56 w-[540px] -translate-x-1/2 rounded-full bg-[linear-gradient(90deg,rgba(75,57,255,0.18),rgba(138,125,255,0.10))] blur-3xl"
                aria-hidden="true"
              />

              <!-- Desktop / Tablet: настоящая «богатая» таблица -->
              <div class="relative hidden lg:block">
                <!-- Header -->
                <div class="grid grid-cols-[minmax(260px,0.34fr)_minmax(0,0.33fr)_minmax(0,0.33fr)] px-8 pt-8">
                  <div class="pr-6">
                    <div class="text-[14px] font-semibold tracking-[-0.01em] text-[#2F3452]">
                      Эффективные растут, неэффективные исчезают
                    </div>
                    <div class="mt-2 max-w-[520px] text-[14px] leading-[1.45] text-[#616782]">
                      Сравнение по ключевым этапам продаж: скорость, качество, устойчивость и масштабирование.
                    </div>
                  </div>

                  <div class="px-2">
                    <div
                      class="compare-pill compare-pill--ai inline-flex w-full items-center justify-center gap-3 rounded-[18px] border border-white/40 bg-[linear-gradient(135deg,rgba(75,57,255,0.10)_0%,rgba(138,125,255,0.08)_100%)] px-5 py-4 shadow-[0_18px_50px_rgba(89,75,255,0.18)] backdrop-blur"
                    >
                      <span
                        class="grid h-9 w-9 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_26px_rgba(89,75,255,0.32)]"
                      >
                        <img src="/vecor.svg" alt="" class="h-4 w-4 brightness-[5] saturate-0" aria-hidden="true" />
                      </span>
                      <div class="text-left">
                        <div class="text-[16px] font-semibold tracking-[-0.02em] text-[#141633]">
                          AI-отдел продаж
                        </div>
                        <div class="text-[13px] font-medium text-[#4B39FF]">24/7 • масштабируемый</div>
                      </div>
                    </div>
                  </div>

                  <div class="pl-2">
                    <div
                      class="compare-pill inline-flex w-full items-center justify-center gap-3 rounded-[18px] border border-[#E6EAF4] bg-white/70 px-5 py-4 shadow-[0_16px_44px_rgba(18,26,52,0.06)] backdrop-blur"
                    >
                      <span class="grid h-9 w-9 place-items-center rounded-full bg-[#111827]/5">
                        <span class="text-[16px] font-semibold text-[#2F3452]">👤</span>
                      </span>
                      <div class="text-left">
                        <div class="text-[16px] font-semibold tracking-[-0.02em] text-[#141633]">
                          Менеджер
                        </div>
                        <div class="text-[13px] font-medium text-[#616782]">человек • ограниченный ресурс</div>
                      </div>
                    </div>
                  </div>
                </div>

                <!-- Rows -->
                <div class="mt-6 px-8 pb-8">
                  <div class="compare-table overflow-hidden rounded-[22px] border border-[#E6EAF4] bg-white/55 shadow-[0_22px_70px_rgba(18,26,52,0.08)]">
                    <div class="divide-y divide-[#E8EBF4]">
                      <div
                        v-for="(r, i) in compareRows"
                        :key="i"
                        class="grid grid-cols-[minmax(260px,0.34fr)_minmax(0,0.33fr)_minmax(0,0.33fr)]"
                      >
                        <!-- label -->
                        <div class="px-6 py-6">
                          <div class="text-[16px] font-semibold tracking-[-0.02em] text-[#141633]">
                            {{ r.label }}
                          </div>
                          <div class="mt-1 text-[13px] leading-[1.35] text-[#7A809A]">
                            Ключевое отличие по этому этапу
                          </div>
                        </div>

                        <!-- AI -->
                        <div class="px-6 py-6">
                          <div
                            class="compare-cell compare-cell--ai rounded-[18px] border border-white/40 bg-[linear-gradient(135deg,rgba(75,57,255,0.08)_0%,rgba(138,125,255,0.05)_100%)] p-5 shadow-[0_18px_52px_rgba(89,75,255,0.12)]"
                          >
                            <div class="flex items-start gap-3">
                              <span
                                class="mt-0.5 grid h-7 w-7 shrink-0 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_22px_rgba(89,75,255,0.26)]"
                              >
                                <span class="text-[14px] text-white">✓</span>
                              </span>
                              <div class="text-[15px] leading-[1.55] tracking-[-0.01em] text-[#141633]">
                                {{ r.ai }}
                              </div>
                            </div>
                          </div>
                        </div>

                        <!-- Human -->
                        <div class="px-6 py-6">
                          <div
                            class="compare-cell rounded-[18px] border border-[#E6EAF4] bg-white/75 p-5 shadow-[0_16px_44px_rgba(18,26,52,0.06)]"
                          >
                            <div class="flex items-start gap-3">
                              <span class="mt-0.5 grid h-7 w-7 shrink-0 place-items-center rounded-full bg-[#111827]/5">
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
                  </div>

                  <!-- bottom note -->
                  <div class="mt-5 text-center text-[13px] leading-[1.45] text-[#6B7190]">
                    Итог: AI не устаёт, не теряет качество и масштабируется — менеджер остаётся на закрытие сделок.
                  </div>
                </div>
              </div>

              <!-- Mobile: дорогие карточки -->
              <div class="relative lg:hidden">
                <div class="px-4 pt-6 sm:px-6">
                  <div class="text-[14px] font-semibold tracking-[-0.02em] text-[#141633] sm:text-[15px]">
                    Эффективные растут, неэффективные исчезают
                  </div>
                  <div class="mt-2 text-[13px] leading-[1.5] text-[#616782]">
                    Сравнение AI-отдела продаж и менеджера по ключевым этапам.
                  </div>

                  <div class="mt-4 grid grid-cols-1 gap-2.5 sm:grid-cols-2 sm:gap-3">
                    <div
                      class="compare-pill compare-pill--ai flex items-center gap-3 rounded-[18px] border border-white/40 bg-[linear-gradient(135deg,rgba(75,57,255,0.10)_0%,rgba(138,125,255,0.08)_100%)] px-4 py-3 shadow-[0_18px_50px_rgba(89,75,255,0.18)] backdrop-blur"
                    >
                      <span
                        class="grid h-9 w-9 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_26px_rgba(89,75,255,0.32)]"
                      >
                        <img src="/vecor.svg" alt="" class="h-4 w-4 brightness-[5] saturate-0" aria-hidden="true" />
                      </span>
                      <div>
                        <div class="text-[15px] font-semibold tracking-[-0.02em] text-[#141633]">AI-отдел продаж</div>
                        <div class="text-[12px] font-medium text-[#4B39FF]">24/7 • масштабируемый</div>
                      </div>
                    </div>

                    <div
                      class="compare-pill flex items-center gap-3 rounded-[18px] border border-[#E6EAF4] bg-white/75 px-4 py-3 shadow-[0_16px_44px_rgba(18,26,52,0.06)] backdrop-blur"
                    >
                      <span class="grid h-9 w-9 place-items-center rounded-full bg-[#111827]/5">
                        <span class="text-[16px] font-semibold text-[#2F3452]">👤</span>
                      </span>
                      <div>
                        <div class="text-[15px] font-semibold tracking-[-0.02em] text-[#141633]">Менеджер</div>
                        <div class="text-[12px] font-medium text-[#616782]">человек • ограничен</div>
                      </div>
                    </div>
                  </div>
                </div>

                <div class="mt-5 space-y-4 px-4 pb-6 sm:px-6 sm:pb-8">
                  <div
                    v-for="(r, i) in compareRows"
                    :key="i"
                    class="rounded-[22px] border border-[#E8EBF4] bg-white/75 p-4 shadow-[0_18px_60px_rgba(18,26,52,0.08)]"
                  >
                    <div class="text-[15px] font-semibold tracking-[-0.02em] text-[#141633]">
                      {{ r.label }}
                    </div>

                    <div class="mt-3 grid gap-3">
                      <div
                        class="rounded-[18px] border border-white/40 bg-[linear-gradient(135deg,rgba(75,57,255,0.10)_0%,rgba(138,125,255,0.06)_100%)] p-4 shadow-[0_18px_52px_rgba(89,75,255,0.14)]"
                      >
                        <div class="flex items-center gap-2 text-[12px] font-semibold text-[#4B39FF]">
                          <span class="grid h-6 w-6 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] text-white">✓</span>
                          AI-отдел продаж
                        </div>
                        <div class="mt-2 text-[14px] leading-[1.55] tracking-[-0.01em] text-[#141633]">
                          {{ r.ai }}
                        </div>
                      </div>

                      <div
                        class="rounded-[18px] border border-[#E6EAF4] bg-white/80 p-4 shadow-[0_14px_44px_rgba(18,26,52,0.06)]"
                      >
                        <div class="flex items-center gap-2 text-[12px] font-semibold text-[#2F3452]">
                          <span class="grid h-6 w-6 place-items-center rounded-full bg-[#111827]/5 text-[#2F3452]">—</span>
                          Менеджер
                        </div>
                        <div class="mt-2 text-[14px] leading-[1.55] tracking-[-0.01em] text-[#2B2E3A]">
                          {{ r.human }}
                        </div>
                      </div>
                    </div>
                  </div>

                  <div class="pt-1 text-center text-[13px] leading-[1.45] text-[#6B7190]">
                    Итог: AI масштабируется и не устаёт — менеджер остаётся на закрытие.
                  </div>
                </div>
              </div>

              <!-- супер-тонкая «дорогая» рамка -->
              <div class="pointer-events-none absolute inset-0 rounded-[24px] sm:rounded-[28px]" aria-hidden="true">
                <div class="absolute inset-0 rounded-[24px] sm:rounded-[28px] border border-white/70 opacity-45"></div>
                <div class="absolute inset-[1px] rounded-[23px] sm:rounded-[27px] border border-[#E6EAF4] opacity-80"></div>
              </div>
            </div>
          </div>
          <!-- /NEW -->
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Чуть «премиальности» за счёт микро-текстуры и градиентной подсветки */
.compare-shell {
  background-image:
    radial-gradient(1200px 280px at 50% 0%, rgba(75, 57, 255, 0.06), transparent 60%),
    radial-gradient(900px 260px at 85% 70%, rgba(138, 125, 255, 0.06), transparent 62%),
    linear-gradient(180deg, #ffffff 0%, #f7f8fc 100%);
}

.compare-table {
  backdrop-filter: blur(10px);
}

.compare-pill--ai {
  position: relative;
}
.compare-pill--ai::after {
  content: '';
  position: absolute;
  inset: -1px;
  border-radius: 18px;
  background: radial-gradient(420px 120px at 50% 0%, rgba(75, 57, 255, 0.18), transparent 60%);
  pointer-events: none;
  opacity: 0.6;
}

.compare-cell--ai {
  position: relative;
}
.compare-cell--ai::after {
  content: '';
  position: absolute;
  inset: -1px;
  border-radius: 18px;
  background: radial-gradient(520px 180px at 20% 0%, rgba(75, 57, 255, 0.14), transparent 55%);
  pointer-events: none;
  opacity: 0.55;
}
</style>
<script setup>
import FeatureRow from './_FeatureRow.vue'

const stats = [
  { value: '0 тг', text: 'за установку ИИ' },
  { value: '100%', text: 'верификация от meta, google,\namocrm, bitrix и другие' },
  { value: '24/7', text: 'поддержка от проектных\nменеджеров' },
]

const features = [
  {
    title: 'Upsell и дожим',
    description: 'Дожимает клиентов, используя\nсобранную информацию',
    image: '/messege.png',
    imageAlt: 'Пример сообщения для upsell',
    imageClass: 'w-full max-w-[520px] sm:max-w-[620px] lg:max-w-none lg:w-[1188px]',
    viewportClass:
      'h-[133px] w-full max-w-[320px] overflow-hidden rounded-[14px] sm:max-w-[360px] lg:h-[133px] lg:w-[300px]',
    imageTranslateClass: '-translate-x-[13px] -translate-y-[1px]',
    visualTop: true,
  },
  {
    title: 'Интеграция с CRM',
    description: 'Двигает этапы сделки, заполняет\nполя и ставит задачи',
    image: '/banner 3.png',
    imageAlt: 'Интеграция с amoCRM и Bitrix24',
    imageClass: 'w-[170px] sm:w-[190px] lg:w-[200px]',
  },
  {
    title: 'Запись клиентов',
    description: 'Назначает клиентам встречи\nи записи',
    image: '/banner.png',
    imageAlt: 'Интеграция с календарями',
    imageClass: 'w-[170px] sm:w-[190px] lg:w-[200px]',
  },
  {
    title: 'Работа с файлами',
    description: 'Читает любые файлы',
    image: '/banner 2.png',
    imageAlt: 'Поддерживаемые типы файлов',
    imageClass: 'w-[170px] sm:w-[190px] lg:w-[200px]',
  },
  {
    title: 'Мультиязычность',
    description: 'Идеально говорит на русском,\nанглийском и даже шала-казахском',
    image: '/lang.png',
    imageAlt: 'Поддержка множества языков',
    imageClass: 'w-[170px] sm:w-[190px] lg:w-[200px]',
  },
  {
    title: 'Интеграция с Мойсклад',
    description: 'Знает какой товар есть в наличии',
    image: '/in_nalichii.png',
    imageAlt: 'Статус товара в наличии',
    imageClass: 'w-[170px] sm:w-[190px] lg:w-[200px]',
  },
]
</script>

<template>
  <section id="advantages" class="relative z-10 scroll-mt-[92px] bg-[#F3F4F7] pt-0 pb-12 lg:scroll-mt-[104px]">
    <div class="overflow-x-hidden">
      <div class="mx-auto w-full max-w-[1880px] px-4 sm:px-6 lg:px-10">
        <div class="relative overflow-hidden rounded-t-[20px] bg-white">
          <!-- Статы -->
        <!-- Блок с описанием обучения AI -->
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
                <div class="text-left">
                  <div
                    class="inline-flex items-center gap-2 rounded-full border border-[#E3E7F2] bg-white/90 px-2.5 py-2 shadow-[0_10px_24px_rgba(18,26,52,0.05)] backdrop-blur"
                  >
                    <span
                      class="grid h-6 w-6 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_8px_20px_rgba(89,75,255,0.35)]"
                    >
                      <img src="/vecor.svg" alt="" class="h-3.5 w-3.5 brightness-[5] saturate-0" aria-hidden="true" />
                    </span>
                    <span class="text-[12px] font-medium tracking-[-0.01em] text-[#2F3452] sm:text-[13px]">
                      Обучение AI на ваших данных
                    </span>
                  </div>

                  <p
                    class="mt-4 max-w-[780px] text-[16px] leading-[1.45] tracking-[-0.01em] text-[#2B2E3A] sm:text-[18px] lg:text-[22px]"
                  >
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

                <div
                  class="relative overflow-hidden rounded-[18px] border border-[#D9DEF0] bg-[#171B42] p-4 shadow-[0_24px_60px_rgba(18,26,52,0.18)] sm:rounded-[20px] sm:p-5 lg:p-6"
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
                      class="inline-flex items-center gap-2 rounded-full border border-white/10 bg-white/5 px-3 py-1.5 text-[11px] font-medium text-white/80 sm:text-[12px]"
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

          <!-- Увеличили расстояние между статами и заголовком -->
          <div class="px-4 pb-12 pt-12 text-center sm:px-6 sm:pt-16 lg:px-10 lg:pt-20 lg:pb-14">
            <h2 class="text-[34px] font-semibold leading-[1.06] tracking-[-0.03em] text-[#111218] sm:text-[44px] lg:text-[66px] lg:leading-[1.04]">
              Что умеет
            </h2>
            <p class="mt-2 text-[34px] font-semibold leading-[1.06] tracking-[-0.03em] text-[#9EA4B8] sm:text-[44px] lg:mt-3 lg:text-[66px] lg:leading-[1.04]">
              AI продавец
            </p>
          </div>
        </div>
      </div>
    </div>

    <!-- Фичи -->
    <div class="mt-[18px] overflow-x-hidden">
      <div class="mx-auto w-full max-w-[1760px] px-4 sm:px-6 lg:px-10">
        <!-- ВАЖНО: даём чуть больше правого воздуха, чтобы визуально правая колонка не "уезжала" -->
        <div class="space-y-[14px] lg:space-y-[18px]">
          <FeatureRow
            v-for="feature in features"
            :key="feature.title"
            :title="feature.title"
            :description="feature.description"
            :visual-top="feature.visualTop"
          >
            <!-- ВАЖНО: на lg+ делаем justify-end (контент прижат вправо),
                 на мобилке центр. Это убирает ощущение "съехало влево". -->
            <div class="flex h-auto w-full items-center justify-center py-3 lg:h-[136px] lg:w-full lg:justify-end lg:py-0">
              <div
                v-if="feature.viewportClass"
                :class="[feature.viewportClass, 'mx-auto lg:mx-0']"
              >
                <img
                  :src="feature.image"
                  :alt="feature.imageAlt"
                  :class="[feature.imageClass, feature.imageTranslateClass]"
                  class="h-auto w-full object-contain"
                  loading="lazy"
                  draggable="false"
                />
              </div>

              <img
                v-else
                :src="feature.image"
                :alt="feature.imageAlt"
                :class="[feature.imageClass, 'mx-auto lg:mx-0']"
                class="h-auto max-w-full object-contain"
                loading="lazy"
                draggable="false"
              />
            </div>
          </FeatureRow>
        </div>
      </div>
    </div>
  </section>
</template>

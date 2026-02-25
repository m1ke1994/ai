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
          <div class="px-4 pt-16 pb-8 sm:px-6 lg:px-0 lg:pt-[48px] lg:pb-[22px]">
            <div class="grid grid-cols-1 gap-8 sm:gap-10 md:grid-cols-3 md:gap-0">
              <div
                v-for="(item, index) in stats"
                :key="item.value"
                class="relative px-0 text-center md:px-6 lg:px-[44px]"
              >
                <div
                  v-if="index < stats.length - 1"
                  class="absolute right-0 top-[4px] hidden h-[220px] w-px bg-[#E4E6EE] md:block lg:h-[258px]"
                  aria-hidden="true"
                />

                <p class="text-[44px] font-semibold leading-none tracking-[-0.03em] text-[#10101A] sm:text-[54px] lg:text-[70px]">
                  {{ item.value }}
                </p>

                <p class="mt-5 whitespace-pre-line text-[16px] leading-[1.35] tracking-[-0.01em] text-[#666A7B] sm:text-[18px] lg:mt-8 lg:text-[24px] lg:leading-[1.28]">
                  {{ item.text }}
                </p>

                <div
                  v-if="index < stats.length - 1"
                  class="mx-auto mt-8 h-px w-[92%] bg-[#E4E6EE] md:hidden"
                  aria-hidden="true"
                />
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

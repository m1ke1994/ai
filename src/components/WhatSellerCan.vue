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
    imageClass: 'w-[1188px] max-w-none',
    viewportClass: 'h-[133px] w-[300px] overflow-hidden rounded-[14px]',
    imageTranslateClass: '-translate-x-[13px] -translate-y-[1px]',
    visualTop: true,
  },
  {
    title: 'Интеграция с CRM',
    description: 'Двигает этапы сделки, заполняет\nполя и ставит задачи',
    image: '/banner 3.png',
    imageAlt: 'Интеграция с amoCRM и Bitrix24',
    imageClass: 'w-[200px]',
  },
  {
    title: 'Запись клиентов',
    description: 'Назначает клиентам встречи\nи записи',
    image: '/banner.png',
    imageAlt: 'Интеграция с календарями',
    imageClass: 'w-[200px]',
  },
  {
    title: 'Работа с файлами',
    description: 'Читает любые файлы',
    image: '/banner 2.png',
    imageAlt: 'Поддерживаемые типы файлов',
    imageClass: 'w-[200px]',
  },
  {
    title: 'Мультиязычность',
    description: 'Идеально говорит на русском,\nанглийском и даже шала-казахском',
    image: '/lang.png',
    imageAlt: 'Поддержка множества языков',
    imageClass: 'w-[200px]',
  },
  {
    title: 'Интеграция с Мойсклад',
    description: 'Знает какой товар есть в наличии',
    image: '/in_nalichii.png',
    imageAlt: 'Статус товара в наличии',
    imageClass: 'w-[200px]',
  },
]
</script>

<template>
  <section class="relative z-10 bg-[#F3F4F7] pt-0 pb-12 rounded-none sm:rounded-[40px]">
    <!-- Верхняя часть со статами: на мобилке колонка, на lg как было -->
    <div class="overflow-x-auto lg:overflow-visible">
      <div class="mx-auto min-w-0 lg:min-w-[1860px] max-w-[1880px] px-[6px]">
        <div class="relative overflow-hidden rounded-t-[20px] bg-white">
          <!-- высоту делаем авто на мобилке, фикс на lg -->
          <div class="px-4 pt-10 pb-8 lg:px-0 lg:pt-0 lg:pb-0">
            <div class="grid grid-cols-1 gap-8 lg:grid-cols-3 lg:gap-0 lg:pt-[62px]">
              <div
                v-for="(item, index) in stats"
                :key="item.value"
                class="relative px-0 text-center lg:px-[44px]"
              >
                <!-- вертикальные разделители только на lg -->
                <div
                  v-if="index < stats.length - 1"
                  class="absolute right-0 top-[4px] hidden h-[258px] w-px bg-[#E4E6EE] lg:block"
                  aria-hidden="true"
                />

                <p class="text-[44px] font-semibold leading-none tracking-[-0.03em] text-[#10101A] sm:text-[54px] lg:text-[70px]">
                  {{ item.value }}
                </p>
                <p class="mt-5 whitespace-pre-line text-[16px] leading-[1.35] tracking-[-0.01em] text-[#666A7B] sm:text-[18px] lg:mt-11 lg:text-[24px] lg:leading-[1.28]">
                  {{ item.text }}
                </p>

                <!-- горизонтальный разделитель между элементами на мобилке -->
                <div
                  v-if="index < stats.length - 1"
                  class="mx-auto mt-8 h-px w-[92%] bg-[#E4E6EE] lg:hidden"
                  aria-hidden="true"
                />
              </div>
            </div>
          </div>

          <!-- Заголовок: на мобилке обычный поток, на lg как было (absolute) -->
          <div class="px-4 pb-10 text-center lg:absolute lg:inset-x-0 lg:bottom-[42px] lg:px-10">
            <h2 class="text-[34px] font-semibold leading-[1.06] tracking-[-0.03em] text-[#111218] sm:text-[44px] lg:text-[66px] lg:leading-[1.04]">
              Что умеет
            </h2>
            <p class="mt-2 text-[34px] font-semibold leading-[1.06] tracking-[-0.03em] text-[#9EA4B8] sm:text-[44px] lg:mt-4 lg:text-[66px] lg:leading-[1.04]">
              AI продавец
            </p>
          </div>

          <!-- фикс высоты только на lg (чтобы совпало с прежней версткой) -->
          <div class="hidden lg:block h-[615px]" aria-hidden="true" />
        </div>
      </div>
    </div>

    <!-- Список фич: на мобилке колонка без горизонтального скролла -->
    <div class="mt-[18px] overflow-x-visible lg:overflow-x-auto">
      <div class="mx-auto min-w-0 lg:min-w-[1760px] max-w-[1760px] px-4 sm:px-6">
        <div class="space-y-[14px] lg:space-y-[18px]">
          <FeatureRow
            v-for="feature in features"
            :key="feature.title"
            :title="feature.title"
            :description="feature.description"
            :visual-top="feature.visualTop"
          >
            <!-- на мобилке делаем визуал по центру и ужимаем -->
            <div class="flex h-auto w-full items-center justify-center py-3 lg:h-[136px] lg:w-[440px] lg:justify-start lg:py-0">
              <div v-if="feature.viewportClass" :class="[feature.viewportClass, 'mx-auto lg:mx-0']">
                <img
                  :src="feature.image"
                  :alt="feature.imageAlt"
                  :class="[feature.imageClass, feature.imageTranslateClass]"
                  class="h-auto object-contain"
                  loading="lazy"
                  draggable="false"
                />
              </div>

              <img
                v-else
                :src="feature.image"
                :alt="feature.imageAlt"
                :class="[feature.imageClass, 'mx-auto lg:mx-0']"
                class="h-auto object-contain"
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

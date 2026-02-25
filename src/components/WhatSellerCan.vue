<script setup>
import FeatureRow from './_FeatureRow.vue'

const stats = [
  {
    value: '0 тг',
    text: 'за установку ИИ',
  },
  {
    value: '100%',
    text: 'верификация от meta, google,\namocrm, bitrix и другие',
  },
  {
    value: '24/7',
    text: 'поддержка от проектных\nменеджеров',
  },
]

const features = [
  {
    title: 'Upsell и дожим',
    description: 'Дожимает клиентов, используя\nсобранную информацию',
    image: '/messege.png',
    imageAlt: 'Пример сообщения для upsell',
    imageClass: 'w-[1188px] max-w-none',
    viewportClass: 'h-[133px] w-[325px] overflow-hidden rounded-[14px]',
    imageTranslateClass: '-translate-x-[13px] -translate-y-[1px]',
    visualTop: true,
  },
  {
    title: 'Интеграция с CRM',
    description: 'Двигает этапы сделки, заполняет\nполя и ставит задачи',
    image: '/banner 3.png',
    imageAlt: 'Интеграция с amoCRM и Bitrix24',
    imageClass: 'w-[325px]',
  },
  {
    title: 'Запись клиентов',
    description: 'Назначает клиентам встречи\nи записи',
    image: '/banner.png',
    imageAlt: 'Интеграция с календарями',
    imageClass: 'w-[318px]',
  },
  {
    title: 'Работа с файлами',
    description: 'Читает любые файлы',
    image: '/banner 2.png',
    imageAlt: 'Поддерживаемые типы файлов',
    imageClass: 'w-[392px]',
  },
  {
    title: 'Мультиязычность',
    description: 'Идеально говорит на русском,\nанглийском и даже шала-казахском',
    image: '/lang.png',
    imageAlt: 'Поддержка множества языков',
    imageClass: 'w-[440px]',
  },
  {
    title: 'Интеграция с Мойсклад',
    description: 'Знает какой товар есть в наличии',
    image: '/in_nalichii.png',
    imageAlt: 'Статус товара в наличии',
    imageClass: 'w-[513px]',
  },
]
</script>

<template>
  <section class="relative z-10 bg-[#F3F4F7] pt-0 pb-12">
    <div class="overflow-x-auto">
      <div class="mx-auto min-w-[1860px] max-w-[1880px] px-[6px]">
        <div class="relative h-[615px] overflow-hidden rounded-t-[20px] bg-white">
          <div class="grid grid-cols-3 pt-[62px]">
          <div
            v-for="(item, index) in stats"
            :key="item.value"
            class="relative px-[44px] py-0 text-center"
          >
            <div
              v-if="index < stats.length - 1"
              class="absolute right-0 top-[4px] h-[258px] w-px bg-[#E4E6EE]"
              aria-hidden="true"
            />

            <p class="text-[70px] font-semibold leading-none tracking-[-0.03em] text-[#10101A]">
              {{ item.value }}
            </p>
            <p class="mt-11 whitespace-pre-line text-[24px] leading-[1.28] tracking-[-0.01em] text-[#666A7B]">
              {{ item.text }}
            </p>
          </div>
        </div>

          <div class="absolute inset-x-0 bottom-[42px] px-10 text-center">
            <h2 class="text-[66px] font-semibold leading-[1.04] tracking-[-0.03em] text-[#111218]">
            Что умеет
            </h2>
            <p class="mt-4 text-[66px] font-semibold leading-[1.04] tracking-[-0.03em] text-[#9EA4B8]">
            AI продавец
            </p>
          </div>
        </div>
      </div>
    </div>

    <div class="mt-[18px] overflow-x-auto">
      <div class="mx-auto min-w-[1760px] max-w-[1760px] px-6">
        <div class="space-y-[18px]">
        <FeatureRow
          v-for="feature in features"
          :key="feature.title"
          :title="feature.title"
          :description="feature.description"
          :visual-top="feature.visualTop"
        >
            <div
              v-if="feature.viewportClass"
              :class="feature.viewportClass"
            >
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
              :class="feature.imageClass"
              class="h-auto object-contain"
              loading="lazy"
              draggable="false"
            />
        </FeatureRow>
        </div>
      </div>
    </div>
  </section>
</template>

<template>
  <section class="relative isolate bg-[#F3F4F7] py-28 rounded-[40px]">
    <!-- Заголовок -->
    <div class="text-center">
      <h2 class="text-[48px] font-semibold tracking-[-0.02em] !text-black">
        Этапы интеграции
      </h2>
      <h3 class="mt-4 text-[48px] font-semibold tracking-[-0.02em] !text-gray-400">
        AI-продавца
      </h3>
    </div>

    <div class="max-w-[1320px] mx-auto mt-20 px-6">

      <!-- Первая строка -->
      <div class="grid grid-cols-3 gap-10">
        <div
          v-for="(step, index) in integrationSteps.slice(0, 3)"
          :key="index"
          class="relative flex h-[520px] flex-col justify-between rounded-[32px] bg-[#E9EBF2] p-10"
        >
          <!-- Текст -->
          <div>
            <p class="text-lg !text-gray-500">
              {{ step.day }}
            </p>

            <h4 class="mt-3 text-2xl font-semibold leading-tight !text-black">
              {{ step.title }}
            </h4>

            <p class="mt-4 leading-relaxed !text-gray-500">
              {{ step.desc }}
            </p>
          </div>

          <!-- Контейнер изображения -->
          <div class="mt-6 flex h-[220px] items-center justify-center">
            <img
              v-if="step.image"
              :src="step.image"
              alt=""
              class="max-h-[220px] w-auto object-contain"
            />
          </div>
        </div>
      </div>

      <!-- Вторая строка (та же ширина колонок!) -->
      <div class="grid grid-cols-3 gap-10 mt-10">
        <div
          v-for="(step, index) in integrationSteps.slice(3, 5)"
          :key="index"
          class="relative flex h-[520px] flex-col justify-between rounded-[32px] bg-[#E9EBF2] p-10"
        >
          <!-- Текст -->
          <div>
            <p class="text-lg !text-gray-500">
              {{ step.day }}
            </p>

            <h4 class="mt-3 text-2xl font-semibold leading-tight !text-black">
              {{ step.title }}
            </h4>

            <p class="mt-4 leading-relaxed !text-gray-500">
              {{ step.desc }}
            </p>
          </div>

          <!-- Контейнер изображения -->
          <div class="mt-6 flex h-[220px] items-center justify-center">
            <img
              v-if="step.image"
              :src="step.image"
              alt=""
              class="max-h-[220px] w-auto object-contain"
            />
          </div>
        </div>

        <!-- Пустая колонка для симметрии -->
        <div
          class="relative flex h-[520px] flex-col justify-between overflow-hidden rounded-[32px] bg-[#1B1730] p-10"
        >
          <img
            src="/bg.png"
            alt=""
            aria-hidden="true"
            class="pointer-events-none absolute inset-0 h-full w-full object-cover"
          />
          <div
            aria-hidden="true"
            class="absolute inset-0 bg-[linear-gradient(180deg,rgba(20,16,34,0.35)_0%,rgba(44,31,85,0.52)_50%,rgba(74,56,145,0.78)_100%)]"
          ></div>

          <div class="relative z-10">
            <p class="text-lg font-medium tracking-[-0.01em] text-white/85">
              Готовы начать ?
            </p>

            <h4 class="mt-4 text-[40px] font-semibold leading-[0.96] tracking-[-0.03em] text-white">
              Оставьте заявку<br />
              на консультацию
            </h4>
          </div>

          <button
            type="button"
            class="relative z-10 inline-flex h-[56px] w-[230px] items-center justify-center rounded-[16px] border border-white/60 bg-white/10 text-[18px] font-medium tracking-[-0.01em] text-white backdrop-blur-md transition hover:bg-white/20"
            @click="openContactFormModal"
          >
            Оставить заявку
          </button>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
const CONTACT_FORM_OPEN_EVENT = 'contact-feedback-form:open'

const openContactFormModal = () => {
  if (typeof window !== 'undefined') {
    window.dispatchEvent(new Event(CONTACT_FORM_OPEN_EVENT))
  }
}

const integrationSteps = [
  {
    day: "День 1",
    title: "Брифинг",
    desc: "Проводим интервью, узнаем все необходимое для настройки бота",
    image: "/13.png"
  },
  {
    day: "День 2",
    title: "Создание бота",
    desc: "Технические и sales-специалисты разрабатывают логику и сценарии работы AI-продавца",
    image: "/11.png"
  },
  {
    day: "День 3",
    title: "Тестирование чат-бота",
    desc: "Создаем прототип бота и проводим тестирование сценариев общения",
    image: "/12.png"
  },
  {
    day: "День 4",
    title: "Релиз чат-бота",
    desc: "Подключаем чат-бота ко всем мессенджерам и интегрируем в вашу CRM",
    image: "/icon icon.png"
  },
  {
    day: "Каждый месяц",
    title: "Поддержка и аналитика",
    desc: "Следим за качеством ответов и предоставляем отчеты о работе AI-продавца",
    image: "/10.png"
  }
]
</script>

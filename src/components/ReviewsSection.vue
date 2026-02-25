<template>
  <section
    id="reviews"
    class="scroll-mt-[110px] bg-[#020205] py-20 sm:py-24 lg:py-28 rounded-[40px]"
    aria-labelledby="reviews-title"
  >
    <div class="mx-auto max-w-[1720px] px-4 sm:px-6 lg:px-10">
      <div class="flex flex-col gap-8 md:flex-row md:items-start md:justify-between">
        <div class="max-w-[640px]">
          <h2
            id="reviews-title"
            class="text-[42px] font-semibold leading-[0.95] tracking-[-0.03em] text-white sm:text-[56px] lg:text-[74px]"
          >
            Нам доверили.
            <span class="mt-2 block text-[#A8ADC4]">И не пожалели.</span>
          </h2>
        </div>

        <div class="flex items-center gap-3 md:pt-5">
          <button
            type="button"
            class="inline-flex h-12 w-12 items-center justify-center rounded-full border border-white/10 bg-[#151723] text-[#D8DBEF] transition hover:border-white/25 hover:bg-[#1A1D2B] disabled:cursor-not-allowed disabled:opacity-40"
            :disabled="pageCount <= 1"
            aria-label="Предыдущая группа отзывов"
            @click="goPrev"
          >
            <svg viewBox="0 0 20 20" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.75">
              <path d="M11.75 4.25 6 10l5.75 5.75" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
          </button>

          <button
            type="button"
            class="inline-flex h-12 w-12 items-center justify-center rounded-full border border-white/10 bg-[#151723] text-[#D8DBEF] transition hover:border-white/25 hover:bg-[#1A1D2B] disabled:cursor-not-allowed disabled:opacity-40"
            :disabled="pageCount <= 1"
            aria-label="Следующая группа отзывов"
            @click="goNext"
          >
            <svg viewBox="0 0 20 20" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.75">
              <path d="M8.25 4.25 14 10l-5.75 5.75" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
          </button>
        </div>
      </div>

      <div class="mt-10 overflow-hidden sm:mt-12">
        <div
          class="flex transition-transform duration-500 ease-out"
          :style="{ transform: `translateX(-${currentPage * 100}%)` }"
        >
          <div
            v-for="(page, pageIndex) in pagedReviews"
            :key="`reviews-page-${pageIndex}`"
            class="min-w-full"
          >
            <div
              class="grid gap-6 lg:gap-8"
              :class="gridColumnsClass"
            >
              <article
                v-for="review in page"
                :key="review.id"
                class="flex h-[520px] flex-col rounded-[28px] border border-white/5 bg-[#1F2230] p-8 text-left shadow-[0_20px_60px_rgba(0,0,0,0.28)] lg:p-10"
              >
                <div class="min-h-0 flex-1 overflow-hidden">
                  <h3 class="text-[28px] font-medium leading-tight tracking-[-0.02em] text-white">
                    {{ review.company }}
                  </h3>

                  <p class="mt-4 text-[15px] font-semibold leading-snug text-[#A8ADC4]">
                    {{ review.person }}
                  </p>

                  <div class="mt-6 space-y-4 text-[14px] leading-[1.55] text-[#C4C8DD] sm:text-[15px]">
                    <p v-for="(paragraph, idx) in review.previewParagraphs" :key="`${review.id}-p-${idx}`">
                      {{ paragraph }}
                    </p>

                    <ul
                      v-if="review.previewBullets?.length"
                      class="list-disc space-y-1.5 pl-5 marker:text-[#A7ACC3]"
                    >
                      <li v-for="(bullet, idx) in review.previewBullets" :key="`${review.id}-b-${idx}`">
                        {{ bullet }}
                      </li>
                    </ul>
                  </div>
                </div>

                <button
                  type="button"
                  class="mt-auto inline-flex h-[50px] w-[192px] shrink-0 items-center justify-center rounded-[14px] border border-white/60 bg-transparent text-[18px] font-semibold tracking-[-0.01em] text-white transition hover:bg-white hover:text-black focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-white/70"
                  @click="openReview(review)"
                >
                  Читать далее
                </button>
              </article>
            </div>
          </div>
        </div>
      </div>

      <div
        v-if="pageCount > 1"
        class="mt-6 flex items-center justify-center gap-2"
        aria-label="Индикатор страниц отзывов"
      >
        <button
          v-for="page in pageCount"
          :key="`dot-${page}`"
          type="button"
          class="h-2 rounded-full transition"
          :class="page - 1 === currentPage ? 'w-8 bg-white' : 'w-2 bg-white/25 hover:bg-white/45'"
          :aria-label="`Перейти к странице отзывов ${page}`"
          :aria-current="page - 1 === currentPage ? 'true' : 'false'"
          @click="currentPage = page - 1"
        />
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
        v-if="activeReview"
        class="fixed inset-0 z-[220] bg-black/75 p-4 backdrop-blur-sm sm:p-6"
        role="dialog"
        aria-modal="true"
        :aria-labelledby="`review-modal-title-${activeReview.id}`"
        @click.self="closeReview"
      >
        <div class="flex min-h-full items-center justify-center">
          <Transition
            enter-active-class="transition duration-200 ease-out"
            enter-from-class="translate-y-2 scale-[0.98] opacity-0"
            enter-to-class="translate-y-0 scale-100 opacity-100"
            leave-active-class="transition duration-150 ease-in"
            leave-from-class="translate-y-0 scale-100 opacity-100"
            leave-to-class="translate-y-2 scale-[0.98] opacity-0"
            appear
          >
            <div
              v-if="activeReview"
              class="w-full max-w-4xl overflow-hidden rounded-[24px] border border-white/10 bg-[#121420] shadow-[0_30px_100px_rgba(0,0,0,0.55)]"
            >
              <div class="flex items-start justify-between gap-4 border-b border-white/10 px-5 py-5 sm:px-7">
                <div>
                  <h3
                    :id="`review-modal-title-${activeReview.id}`"
                    class="text-2xl font-semibold tracking-[-0.02em] text-white sm:text-[30px]"
                  >
                    {{ activeReview.company }}
                  </h3>
                  <p class="mt-2 text-sm font-medium text-[#A8ADC4] sm:text-base">
                    {{ activeReview.person }}
                  </p>
                </div>

                <button
                  ref="closeButtonRef"
                  type="button"
                  class="inline-flex h-10 w-10 shrink-0 items-center justify-center rounded-full border border-white/10 bg-white/5 text-white transition hover:bg-white/10 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-white/60"
                  aria-label="Закрыть окно отзыва"
                  @click="closeReview"
                >
                  <svg viewBox="0 0 20 20" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.75">
                    <path d="M5 5l10 10M15 5 5 15" stroke-linecap="round" />
                  </svg>
                </button>
              </div>

              <div class="max-h-[70vh] overflow-y-auto px-5 py-6 sm:px-7 sm:py-7">
                <div class="space-y-5 text-[15px] leading-[1.65] text-[#D4D8EA] sm:text-base">
                  <p v-for="(paragraph, idx) in activeReview.detailsParagraphs" :key="`${activeReview.id}-detail-${idx}`">
                    {{ paragraph }}
                  </p>

                  <div v-if="activeReview.results?.length" class="rounded-2xl border border-white/8 bg-white/3 p-4 sm:p-5">
                    <p class="text-sm font-semibold uppercase tracking-[0.08em] text-[#A8ADC4]">
                      Результаты
                    </p>
                    <ul class="mt-3 list-disc space-y-2 pl-5 marker:text-[#C4C8DD]">
                      <li v-for="(result, idx) in activeReview.results" :key="`${activeReview.id}-result-${idx}`">
                        {{ result }}
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </Transition>
        </div>
      </div>
    </Transition>
  </Teleport>
</template>

<script setup>
import { computed, nextTick, onBeforeUnmount, onMounted, ref, watch } from 'vue'

const reviews = [
  {
    id: 'impact',
    company: 'Impact',
    person: 'Жанибек, коммерческий директор Impact',
    previewParagraphs: [
      'В феврале 2025 года мы внедрили ИИ-бота MoonAI для взаимодействия с клиентами. Результаты превзошли ожидания:',
    ],
    previewBullets: [
      'количество обработанных заявок выросло в 2 раза',
      'скорость ответа сократилась с 5–10 минут до 5 секунд',
      '19% обращений закрываются полностью без участия менеджеров',
      'уровень удовлетворённости клиентов вырос и продолжает расти...',
    ],
    detailsParagraphs: [
      'Мы внедрили MoonAI в отдел первичных обращений, чтобы разгрузить менеджеров и ускорить ответ клиентам в часы пик.',
      'Система взяла на себя приветствие, квалификацию, ответы на частые вопросы и сбор первичной информации перед передачей менеджеру.',
      'Отдельно ценим, что команда MoonAI помогла адаптировать сценарии под наши процессы и быстро внесла правки после запуска.',
    ],
    results: [
      'Количество обработанных заявок выросло в 2 раза',
      'Среднее время первого ответа сократилось до 5 секунд',
      '19% обращений бот закрывает без участия менеджера',
      'Клиенты стали чаще доходить до целевого действия',
    ],
  },
  {
    id: 'zhanalim',
    company: 'ZhanAlim Travel',
    person: 'Ерболат',
    previewParagraphs: [
      'После внедрения ИИ в наш WhatsApp, где он приветствует и квалифицирует клиентов, качество лидов заметно выросло.',
      'Теперь менеджеры не тратят время на «пустые» заявки и сосредотачиваются только на целевых клиентах.',
      'MoonAI отлично заменяет менеджера на начальных этапах...',
    ],
    previewBullets: [],
    detailsParagraphs: [
      'MoonAI обрабатывает поток входящих запросов в WhatsApp и задаёт ключевые вопросы ещё до подключения менеджера.',
      'За счёт автоматической квалификации мы быстрее понимаем намерение клиента и распределяем лиды по нужным направлениям.',
      'Это сократило нагрузку на команду и повысило конверсию из первичного обращения в диалог с менеджером.',
    ],
    results: [
      'Качество лидов выросло за счёт предварительной квалификации',
      'Менеджеры работают только с релевантными обращениями',
      'Ускорилась обработка заявок в мессенджерах',
    ],
  },
  {
    id: 'abasqar',
    company: 'Abasqar_kz',
    person: 'Сырым, менеджер компании',
    previewParagraphs: [
      'Мы заменили менеджера по технической поддержке на искусственный интеллект. До внедрения мы не успевали отвечать всем клиентам.',
      'Главное преимущество в том, что клиент вместо ожидания ответа он сразу получает решение...',
    ],
    previewBullets: [],
    detailsParagraphs: [
      'До внедрения MoonAI поддержка отвечала с задержкой, а часть обращений терялась в пиковые часы.',
      'После запуска ИИ-бота пользователи сразу получают ответ по типовым вопросам, статусу заказа и базовой диагностике.',
      'Менеджеры подключаются только к нестандартным кейсам, поэтому качество и скорость поддержки заметно выросли.',
    ],
    results: [
      'Сократилось время ожидания ответа',
      'Снизилась нагрузка на менеджеров поддержки',
      'Клиенты быстрее получают решение по стандартным запросам',
    ],
  },
  {
    id: 'edutech',
    company: 'EduPro',
    person: 'Алия, руководитель отдела продаж',
    previewParagraphs: [
      'MoonAI помог автоматизировать запись на пробные уроки и первичную коммуникацию в Instagram и WhatsApp.',
      'Мы быстро протестировали несколько сценариев и оставили тот, который дал лучший отклик.',
    ],
    previewBullets: [],
    detailsParagraphs: [
      'Для нас было важно не просто отвечать быстро, а собирать правильные данные перед звонком менеджера.',
      'MoonAI помогает уточнить возраст ученика, желаемый формат обучения и удобное время для пробного урока.',
      'В результате менеджеры стали тратить меньше времени на переписку и больше на консультации и продажи.',
    ],
    results: [
      'Ускорена запись на пробные занятия',
      'Собирается больше данных до звонка менеджера',
      'Менеджеры концентрируются на продажах, а не на рутине',
    ],
  },
  {
    id: 'retailhub',
    company: 'RetailHub',
    person: 'Арман, операционный директор',
    previewParagraphs: [
      'Интегрировали MoonAI с CRM и складским учётом. Бот начал сразу отвечать по наличию товара и статусу заказа.',
      'Это снизило количество однотипных обращений к менеджерам и ускорило обработку заказов.',
    ],
    previewBullets: [],
    detailsParagraphs: [
      'Основной запрос клиентов — наличие, сроки доставки и повторные заказы. Раньше на это уходило слишком много времени менеджеров.',
      'После интеграции с CRM и складом бот отвечает автоматически и корректно передаёт сложные обращения в нужный отдел.',
      'Команда MoonAI помогла с настройкой сценариев и контролем качества ответов в первые недели.',
    ],
    results: [
      'Снижено число рутинных обращений к менеджерам',
      'Ускорены ответы по наличию и статусам заказов',
      'Повышена точность передачи обращений в отделы',
    ],
  },
  {
    id: 'medcenter',
    company: 'MedLine',
    person: 'Нурлан, управляющий клиники',
    previewParagraphs: [
      'Используем MoonAI для первичной записи пациентов и ответов на типовые вопросы по услугам клиники.',
      'Бот работает круглосуточно и помогает не терять заявки в нерабочее время.',
    ],
    previewBullets: [],
    detailsParagraphs: [
      'Для клиники критично быстро отвечать новым пациентам, особенно вечером и в выходные. MoonAI закрывает эту задачу 24/7.',
      'Бот подсказывает доступные услуги, собирает контакты и предпочтительное время, а затем передаёт запись администратору.',
      'Мы видим стабильный поток заявок и меньше пропущенных обращений.',
    ],
    results: [
      'Заявки принимаются 24/7',
      'Снижено число пропущенных обращений',
      'Администраторы тратят меньше времени на однотипные ответы',
    ],
  },
]

const viewportWidth = ref(typeof window !== 'undefined' ? window.innerWidth : 1440)
const currentPage = ref(0)
const activeReview = ref(null)
const closeButtonRef = ref(null)
let previousBodyOverflow = ''

const cardsPerPage = computed(() => {
  if (viewportWidth.value >= 1280) return 3
  if (viewportWidth.value >= 768) return 2
  return 1
})

const pagedReviews = computed(() => {
  const perPage = cardsPerPage.value
  const pages = []

  for (let i = 0; i < reviews.length; i += perPage) {
    pages.push(reviews.slice(i, i + perPage))
  }

  return pages
})

const pageCount = computed(() => pagedReviews.value.length)

const gridColumnsClass = computed(() => {
  if (cardsPerPage.value === 3) return 'grid-cols-3'
  if (cardsPerPage.value === 2) return 'grid-cols-2'
  return 'grid-cols-1'
})

const updateViewportWidth = () => {
  viewportWidth.value = window.innerWidth
}

const goPrev = () => {
  if (pageCount.value <= 1) return
  currentPage.value = (currentPage.value - 1 + pageCount.value) % pageCount.value
}

const goNext = () => {
  if (pageCount.value <= 1) return
  currentPage.value = (currentPage.value + 1) % pageCount.value
}

const openReview = async (review) => {
  activeReview.value = review
  await nextTick()
  closeButtonRef.value?.focus()
}

const closeReview = () => {
  activeReview.value = null
}

const handleKeydown = (event) => {
  if (event.key === 'Escape' && activeReview.value) {
    closeReview()
    return
  }

  if (event.key === 'ArrowLeft' && !activeReview.value) {
    goPrev()
  }

  if (event.key === 'ArrowRight' && !activeReview.value) {
    goNext()
  }
}

watch(pageCount, (count) => {
  if (count === 0) {
    currentPage.value = 0
    return
  }

  if (currentPage.value > count - 1) {
    currentPage.value = count - 1
  }
})

watch(activeReview, (review) => {
  if (typeof document === 'undefined') return

  if (review) {
    previousBodyOverflow = document.body.style.overflow
    document.body.style.overflow = 'hidden'
    return
  }

  document.body.style.overflow = previousBodyOverflow
})

onMounted(() => {
  updateViewportWidth()
  window.addEventListener('resize', updateViewportWidth)
  window.addEventListener('keydown', handleKeydown)
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', updateViewportWidth)
  window.removeEventListener('keydown', handleKeydown)
  if (typeof document !== 'undefined') {
    document.body.style.overflow = previousBodyOverflow
  }
})
</script>

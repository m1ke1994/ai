<template>
  <section
    id="reviews"
    class="scroll-mt-[92px] bg-[#020205] py-20 sm:py-24 lg:scroll-mt-[104px] lg:py-28 rounded-none sm:rounded-[40px]"
    aria-labelledby="reviews-title"
  >
    <div class="mx-auto max-w-[1720px] px-4 sm:px-6 lg:px-10">
      <div class="flex flex-col gap-8 md:flex-row md:items-start md:justify-between">
        <div class="max-w-[640px]">
          <h2
            id="reviews-title"
            class="text-[42px] font-semibold leading-[0.95] tracking-[-0.03em] text-white sm:text-[56px] lg:text-[54px]"
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
            <div class="grid gap-6 lg:gap-8" :class="gridColumnsClass">
              <article
                v-for="review in page"
                :key="review.id"
                class="flex min-h-[460px] flex-col rounded-[28px] border border-white/5 bg-[#1F2230] p-6 text-left shadow-[0_20px_60px_rgba(0,0,0,0.28)] sm:min-h-[500px] sm:p-8 lg:h-[520px] lg:p-10"
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

                    <ul v-if="review.previewBullets?.length" class="list-disc space-y-1.5 pl-5 marker:text-[#A7ACC3]">
                      <li v-for="(bullet, idx) in review.previewBullets" :key="`${review.id}-b-${idx}`">
                        {{ bullet }}
                      </li>
                    </ul>
                  </div>
                </div>

                <button
                  type="button"
                  class="mt-auto inline-flex h-[50px] w-full max-w-[192px] shrink-0 items-center justify-center rounded-[14px] border border-white/60 bg-transparent text-[18px] font-semibold tracking-[-0.01em] text-white transition hover:bg-white hover:text-black focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-white/70"
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
    id: 'nova-invest',
    company: 'Nova Invest',
    person: 'Андрей, руководитель отдела продаж Nova Invest',
    previewParagraphs: [
      'Подключили MoonAI для первичной консультации и квалификации обращений с сайта. Поток стал обрабатываться быстрее, а менеджеры перестали тонуть в рутине.',
    ],
    previewBullets: [
      'сократили время первого ответа до секунд',
      'стало меньше «пустых» обращений в отделе продаж',
      'клиенты чаще доходят до заявки/звонка',
      'стали стабильнее показатели в выходные и вечером',
    ],
    detailsParagraphs: [
      'Нам было важно быстро отвечать и при этом не терять качество: клиенты часто задают похожие вопросы и ждут понятного, уверенного ответа.',
      'MoonAI взял на себя первичный диалог, уточнение потребностей и сбор контактов. Дальше менеджеры подключаются уже к «тёплым» лидам.',
      'Понравилось, что сценарии подстроили под нашу лексику и правила общения: без воды, по делу, с корректной подачей.',
      'В первые дни после запуска оперативно допилили ответы и формулировки — это сильно ускорило выход на стабильный результат.',
    ],
    results: [
      'Быстрый первый ответ на обращения с сайта',
      'Снижение нагрузки на менеджеров на первичном этапе',
      'Больше квалифицированных лидов в работе',
      'Стабильная обработка заявок вне рабочего времени',
    ],
  },
  {
    id: 'oknabutik',
    company: 'ОкнаБутик',
    person: 'Марина, менеджер по развитию ОкнаБутик',
    previewParagraphs: [
      'Запустили MoonAI, чтобы не терять заявки на расчёт и консультации. Клиенты получают ответы мгновенно, а мы — структурированные данные для расчёта.',
    ],
    previewBullets: [
      'быстрее собираем параметры запроса',
      'меньше «пропущенных» сообщений',
      'менеджеры подключаются уже на этапе расчёта',
    ],
    detailsParagraphs: [
      'Раньше значительная часть времени уходила на повторяющиеся вопросы и уточнение базовых параметров. Это тормозило расчёт и снижало конверсию.',
      'Теперь MoonAI задаёт правильные вопросы по порядку, фиксирует ответы и передаёт менеджеру уже подготовленный запрос.',
      'Отдельно отмечу аккуратный стиль общения: без навязчивости, при этом уверенно ведёт клиента к следующему шагу.',
    ],
    results: [
      'Ускорение сбора данных для расчёта',
      'Снижение доли потерянных обращений',
      'Больше подготовленных заявок для менеджера',
    ],
  },
  {
    id: 'mob-md',
    company: 'MOB.md',
    person: 'Денис, операционный менеджер MOB.md',
    previewParagraphs: [
      'Подключили MoonAI для поддержки и консультаций по услугам/продукту. Стало меньше ожидания, а повторяющиеся вопросы закрываются автоматически.',
    ],
    previewBullets: [
      'меньше нагрузки на поддержку',
      'быстрее ответы по типовым запросам',
      'люди чаще доходят до целевого действия',
    ],
    detailsParagraphs: [
      'Основной запрос был простой: ускорить ответы и разгрузить команду. В часы пик поддержка не успевала, часть клиентов уходила.',
      'MoonAI закрывает типовые вопросы и помогает пользователю сделать следующий шаг: оформить заявку, уточнить детали, оставить контакт.',
      'Самое ценное — стабильность: качество ответа не «плывёт» от усталости, и клиент всегда получает понятную навигацию.',
    ],
    results: [
      'Сокращение времени ожидания ответа',
      'Снижение нагрузки на операторов/менеджеров',
      'Рост доли обращений, доведённых до заявки',
    ],
  },
  {
    id: 'academkids',
    company: 'AcademKids',
    person: 'Ольга, администратор AcademKids',
    previewParagraphs: [
      'MoonAI автоматизировал первичную запись и ответы на частые вопросы родителей. Теперь заявки не теряются вечером и в выходные.',
    ],
    previewBullets: [
      'запись работает 24/7',
      'быстрее собираем данные для администратора',
      'родители получают понятные ответы сразу',
    ],
    detailsParagraphs: [
      'В сфере обучения очень важна скорость реакции: родитель написал — хочет ответ сейчас. Раньше это зависело от загруженности администратора.',
      'MoonAI уточняет возраст, формат, интересующее направление, удобное время и передаёт нам уже готовую заявку.',
      'После запуска мы быстро подправили формулировки под наш тон общения и получили ровный, «брендовый» стиль диалога.',
    ],
    results: [
      'Стабильная запись 24/7',
      'Больше заявок с корректными данными',
      'Меньше ручной рутины у администратора',
    ],
  },
  {
    id: 'ru-biss',
    company: 'RU-BISS',
    person: 'Илья, руководитель проектов RU-BISS',
    previewParagraphs: [
      'Внедрили MoonAI для первичной консультации и маршрутизации обращений. Теперь клиент быстрее попадает в нужный сценарий, а менеджеры — в нужную задачу.',
    ],
    previewBullets: [
      'быстрее квалификация и распределение',
      'меньше разрозненных диалогов',
      'понятная логика общения и фиксация данных',
    ],
    detailsParagraphs: [
      'Нам важно, чтобы клиент сразу получал корректный ответ и понимал дальнейшие шаги. MoonAI помогает держать одинаковое качество коммуникации.',
      'Сценарии настроили так, чтобы бот задавал вопросы по делу и не перегружал клиента лишними деталями.',
      'После внедрения стало проще контролировать входящий поток: диалоги стали структурированными, а менеджеры получили фокус на закрытии.',
    ],
    results: [
      'Ускорение квалификации входящих обращений',
      'Снижение хаоса в коммуникациях',
      'Рост доли обращений, доведённых до следующего шага',
    ],
  },
  {
    id: 'pokolenie-plus',
    company: 'Поколение+',
    person: 'Светлана, управляющая Поколение+',
    previewParagraphs: [
      'MoonAI помог закрыть первичную коммуникацию: ответы на вопросы, запись/заявки и сбор контактов. В результате меньше пропущенных обращений.',
    ],
    previewBullets: [
      'клиенты получают ответ сразу',
      'всё фиксируется и ничего не теряется',
      'команда тратит время на важное, а не на рутину',
    ],
    detailsParagraphs: [
      'Мы искали решение, которое будет вежливо и понятно общаться, но при этом вести клиента к конкретному действию.',
      'MoonAI справился: уточняет запрос, даёт ответы, помогает записаться/оставить заявку и передаёт контакт нам.',
      'Особенно заметен эффект вне рабочего времени — когда раньше часть обращений просто «сгорала».',
    ],
    results: [
      'Сокращение пропущенных обращений',
      'Более стабильный поток заявок в нерабочее время',
      'Разгрузка сотрудников от повторяющихся вопросов',
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
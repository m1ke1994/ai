<template>
  <section
    id="reviews"
    class="scroll-mt-[92px] bg-[#020205] py-8 sm:py-10 lg:scroll-mt-[104px] lg:py-12"
    aria-labelledby="reviews-title"
  >
    <div class="mx-auto max-w-[1720px] px-4 sm:px-6 lg:px-10">
      <div class="flex flex-col gap-8 md:flex-row md:items-start md:justify-between">
        <div class="max-w-[640px]">
          <h2
            id="reviews-title"
            class="text-[42px] font-semibold leading-[0.95] tracking-[-0.03em] text-white sm:text-[56px] lg:text-[54px]"
          >
            {{ reviewsData.titleMain }}
            <span class="mt-2 block text-[#A8ADC4]">{{ reviewsData.titleAccent }}</span>
          </h2>
        </div>

        <div class="flex items-center gap-3 md:pt-5">
          <button
            type="button"
            class="inline-flex h-12 w-12 items-center justify-center rounded-full border border-white/10 bg-[#151723] text-[#D8DBEF] transition hover:border-white/25 hover:bg-[#1A1D2B] disabled:cursor-not-allowed disabled:opacity-40"
            :disabled="pageCount <= 1"
            :aria-label="reviewsData.actions.prevPageAria"
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
            :aria-label="reviewsData.actions.nextPageAria"
            @click="goNext"
          >
            <svg viewBox="0 0 20 20" class="h-5 w-5" fill="none" stroke="currentColor" stroke-width="1.75">
              <path d="M8.25 4.25 14 10l-5.75 5.75" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
          </button>
        </div>
      </div>

      <!-- ВАЖНО: верстку сохраняем, добавляем только “свайп” -->
      <div class="mt-10 overflow-hidden sm:mt-12" ref="viewportRef">
        <div
          ref="trackRef"
          class="flex transition-transform duration-500 ease-out"
          :class="isDragging ? 'duration-0' : ''"
          :style="{
            transform: `translateX(${trackTranslateX}px)`,
            touchAction: 'pan-y',
          }"
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
                  {{ reviewsData.actions.readMore }}
                </button>
              </article>
            </div>
          </div>
        </div>
      </div>

      <div
        v-if="pageCount > 1"
        class="mt-6 flex items-center justify-center gap-2"
        :aria-label="reviewsData.actions.paginationAria"
      >
        <button
          v-for="page in pageCount"
          :key="`dot-${page}`"
          type="button"
          class="h-2 rounded-full transition"
          :class="page - 1 === currentPage ? 'w-8 bg-white' : 'w-2 bg-white/25 hover:bg-white/45'"
          :aria-label="`${reviewsData.actions.paginationGoTo} ${page}`"
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
                  :aria-label="reviewsData.actions.closeModalAria"
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
                      {{ reviewsData.modalResultsTitle }}
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
import { siteData } from '@/assets/data'

const reviewsData = siteData.reviews
const reviews = reviewsData.items

const viewportWidth = ref(typeof window !== 'undefined' ? window.innerWidth : 1440)
const currentPage = ref(0)
const activeReview = ref(null)
const closeButtonRef = ref(null)
let previousBodyOverflow = ''

// refs для свайпа/размера
const viewportRef = ref(null)
const trackRef = ref(null)
const viewportPx = ref(0)

// свайп-состояние
const isDragging = ref(false)
const dragOffsetX = ref(0)
let pointerId = null
let startX = 0
let startY = 0
let lockedAxis = null // 'x' | 'y' | null

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

const updateViewportPx = () => {
  viewportPx.value = viewportRef.value?.clientWidth || 0
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

// --- СВАЙП (Pointer Events) ---
const clamp = (v, min, max) => Math.min(max, Math.max(min, v))

const getSwipeThreshold = () => {
  // чуть “упругий” порог: 15% ширины, но не меньше 50px и не больше 120px
  const w = viewportPx.value || 0
  return clamp(w * 0.15, 50, 120)
}

const onPointerDown = (e) => {
  // модалка открыта — свайп не нужен
  if (activeReview.value) return
  if (pageCount.value <= 1) return

  // только основной палец/кнопка
  if (e.pointerType === 'mouse' && e.button !== 0) return

  pointerId = e.pointerId
  startX = e.clientX
  startY = e.clientY
  lockedAxis = null
  isDragging.value = true
  dragOffsetX.value = 0

  // захватываем pointer, чтобы не “терять” свайп
  trackRef.value?.setPointerCapture?.(pointerId)
}

const onPointerMove = (e) => {
  if (!isDragging.value) return
  if (pointerId !== e.pointerId) return

  const dx = e.clientX - startX
  const dy = e.clientY - startY

  // определяем ось (чтобы вертикальный скролл не ломать)
  if (!lockedAxis) {
    if (Math.abs(dx) < 6 && Math.abs(dy) < 6) return
    lockedAxis = Math.abs(dx) > Math.abs(dy) ? 'x' : 'y'
  }

  if (lockedAxis === 'y') {
    // вертикальный скролл — отпускаем “перетаскивание”
    dragOffsetX.value = 0
    return
  }

  // горизонтальный свайп: гасим нежелательные жесты браузера
  e.preventDefault?.()

  // легкое сопротивление на краях (если вдруг без цикличности пригодится),
  // но у нас цикличная прокрутка — оставим просто ограничение по “упругости”
  const maxPull = (viewportPx.value || 360) * 0.35
  dragOffsetX.value = clamp(dx, -maxPull, maxPull)
}

const finishDrag = () => {
  if (!isDragging.value) return

  const threshold = getSwipeThreshold()
  const dx = dragOffsetX.value

  isDragging.value = false
  dragOffsetX.value = 0
  lockedAxis = null
  pointerId = null

  if (Math.abs(dx) < threshold) return

  // dx < 0 — тянем влево, значит следующий слайд
  if (dx < 0) goNext()
  else goPrev()
}

const onPointerUp = (e) => {
  if (!isDragging.value) return
  if (pointerId !== e.pointerId) return
  finishDrag()
}

const onPointerCancel = (e) => {
  if (!isDragging.value) return
  if (pointerId !== e.pointerId) return
  // просто сброс без перелистывания
  isDragging.value = false
  dragOffsetX.value = 0
  lockedAxis = null
  pointerId = null
}

// px-трансформ вместо % — чтобы во время свайпа можно было двигать на пиксели
const trackTranslateX = computed(() => {
  const w = viewportPx.value || 0
  return -(currentPage.value * w) + dragOffsetX.value
})

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
  updateViewportPx()

  window.addEventListener('resize', updateViewportWidth)
  window.addEventListener('resize', updateViewportPx)
  window.addEventListener('keydown', handleKeydown)

  // Pointer events — свайп и на iOS/Android, и в десктопе (мышкой тоже можно)
  const el = trackRef.value
  if (el) {
    el.addEventListener('pointerdown', onPointerDown, { passive: true })
    // move НЕ passive, чтобы preventDefault работал при горизонтальном свайпе
    el.addEventListener('pointermove', onPointerMove, { passive: false })
    el.addEventListener('pointerup', onPointerUp, { passive: true })
    el.addEventListener('pointercancel', onPointerCancel, { passive: true })
  }

  // на случай, если ширина меняется не только от resize (например, шрифты/контейнер)
  if ('ResizeObserver' in window && viewportRef.value) {
    const ro = new ResizeObserver(() => updateViewportPx())
    ro.observe(viewportRef.value)
    // сохраним в элементе, чтобы снять позже
    viewportRef.value.__ro = ro
  }
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', updateViewportWidth)
  window.removeEventListener('resize', updateViewportPx)
  window.removeEventListener('keydown', handleKeydown)

  const el = trackRef.value
  if (el) {
    el.removeEventListener('pointerdown', onPointerDown)
    el.removeEventListener('pointermove', onPointerMove)
    el.removeEventListener('pointerup', onPointerUp)
    el.removeEventListener('pointercancel', onPointerCancel)
  }

  const ro = viewportRef.value?.__ro
  if (ro?.disconnect) ro.disconnect()

  if (typeof document !== 'undefined') {
    document.body.style.overflow = previousBodyOverflow
  }
})
</script>
<script setup>
import Social_Media from '@/components/Social_Media.vue'
import { siteData } from '@/assets/data'

const aiValueData = siteData.aiValue
const launchData = aiValueData.launch
const integrationsData = aiValueData.integrations
const valuePoints = launchData.valuePoints
const integrationsRows = integrationsData.rows
</script>

<template>
  <section
    id="ai-value"
    class="relative isolate scroll-mt-[92px] rounded-none bg-[#F3F4F7] py-14 lg:scroll-mt-[104px] sm:py-20 lg:py-28"
  >
    <div
      aria-hidden="true"
      class="pointer-events-none absolute inset-0 opacity-100"
      style="
        background:
          radial-gradient(36rem 18rem at 10% 0%, rgba(111, 99, 255, 0.10), transparent 72%),
          radial-gradient(34rem 18rem at 92% 12%, rgba(126, 182, 255, 0.10), transparent 72%),
          radial-gradient(30rem 16rem at 50% 100%, rgba(111, 99, 255, 0.05), transparent 78%);
      "
    />

    <div class="relative z-10 mx-auto w-full max-w-[1760px] px-4 sm:px-6 lg:px-10">
      <!-- Title -->
      <div class="text-center">
        <h2
          class="text-[34px] font-semibold leading-[1.06] tracking-[-0.03em] text-[#111218] sm:text-[44px] lg:text-[66px] lg:leading-[1.04]"
        >
          {{ aiValueData.title }}
        </h2>
        <h3
          class="mt-2 text-[30px] font-semibold leading-[1.06] tracking-[-0.03em] text-[#9EA4B8] sm:text-[40px] lg:mt-3 lg:text-[58px] lg:leading-[1.04]"
        >
          {{ aiValueData.subtitlePrefix }}
          <span class="bg-[linear-gradient(90deg,#5E52DE_0%,#8075FF_55%,#6FA9FF_100%)] bg-clip-text text-transparent">
            {{ aiValueData.subtitleHighlight }}
          </span>
        </h3>
      </div>

      <!-- ✅ Вертикальный стек: 1) запуск, 2) интеграции, 3) каналы -->
      <div class="mt-8 grid grid-cols-1 gap-5 sm:mt-10 lg:gap-6">
        <!-- 1) Запускаем AI-продавца -->
     <div
  class="relative overflow-hidden rounded-[30px] border border-[#DADFF3] bg-[linear-gradient(145deg,rgba(111,99,255,0.10)_0%,rgba(255,255,255,0.95)_35%,rgba(111,99,255,0.04)_100%)] p-5 shadow-[0_24px_70px_rgba(38,44,88,0.10)] sm:rounded-[32px] sm:p-6 lg:p-7"
>
  <div
    aria-hidden="true"
    class="pointer-events-none absolute inset-0 opacity-[0.25]"
    style="
      background-image: repeating-linear-gradient(
        130deg,
        rgba(111, 99, 255, 0.14) 0px,
        rgba(111, 99, 255, 0.14) 1px,
        transparent 1px,
        transparent 14px
      );
    "
  ></div>
  <div
    aria-hidden="true"
    class="pointer-events-none absolute -left-16 -top-16 h-40 w-40 rounded-full bg-[rgba(111,99,255,0.14)] blur-3xl"
  ></div>
  <div
    aria-hidden="true"
    class="pointer-events-none absolute -bottom-12 right-0 h-36 w-36 rounded-full bg-[rgba(126,182,255,0.16)] blur-3xl"
  ></div>

  <div class="relative">
    <div class="flex flex-wrap items-center gap-2.5">
      <span
        class="inline-flex items-center rounded-full border border-[#CFC8FF] bg-[rgba(111,99,255,0.08)] px-3 py-1.5 text-[11px] font-semibold tracking-[0.04em] text-[#5B50CF]"
      >
        {{ launchData.badgePrimary }}
      </span>
      <span
        class="inline-flex items-center rounded-full border border-[#E3E7F4] bg-white/80 px-3 py-1.5 text-[11px] font-medium tracking-[-0.01em] text-[#5B627E]"
      >
        {{ launchData.badgeSecondary }}
      </span>
    </div>

    <h4
      class="mt-4 text-[22px] font-semibold leading-[1.08] tracking-[-0.03em] text-[#141633] sm:text-[26px] lg:text-[30px]"
    >
      {{ launchData.title }}
    </h4>

    <p class="mt-3 max-w-[980px] text-[14px] leading-[1.5] tracking-[-0.01em] text-[#646C89] sm:text-[15px] lg:text-[16px]">
      {{ launchData.description }}
    </p>

    <!-- ✅ ДВЕ КОЛОНКИ В ГОРИЗОНТАЛЬ (всегда рядом) -->
    <div class="mt-6 overflow-hidden rounded-[22px] border border-white/40 bg-white/55 shadow-[0_18px_55px_rgba(18,26,52,0.08)]">
      <div class="relative grid grid-cols-2 gap-0">
        <!-- vertical divider -->
        <div
          class="pointer-events-none absolute inset-y-0 left-1/2 hidden w-px -translate-x-1/2 bg-[linear-gradient(180deg,transparent_0%,rgba(90,98,126,0.18)_16%,rgba(90,98,126,0.18)_84%,transparent_100%)] sm:block"
          aria-hidden="true"
        ></div>
        <div
          class="pointer-events-none absolute inset-y-0 left-1/2 w-px -translate-x-1/2 bg-[linear-gradient(180deg,transparent_0%,rgba(90,98,126,0.18)_16%,rgba(90,98,126,0.18)_84%,transparent_100%)] sm:hidden"
          aria-hidden="true"
        ></div>

        <!-- LEFT: Бесплатная основа -->
        <div class="p-4 sm:p-5 lg:p-6">
          <div class="inline-flex items-center gap-2 rounded-full border border-white/50 bg-white/70 px-3 py-1.5 text-[12px] font-semibold text-[#141633]">
            <span class="h-2 w-2 rounded-full bg-[#78F7C7]" aria-hidden="true"></span>
            {{ launchData.leftLabel }}
          </div>

          <div class="mt-4 grid gap-2.5">
            <div class="flex items-start gap-2.5 rounded-[18px] border border-white/50 bg-white/70 px-3.5 py-3 shadow-[0_14px_36px_rgba(18,26,52,0.05)] backdrop-blur-sm">
              <span
                aria-hidden="true"
                class="mt-0.5 grid h-6 w-6 shrink-0 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_22px_rgba(89,75,255,0.24)]"
              >
                <svg viewBox="0 0 16 16" class="h-3.5 w-3.5 text-white" fill="none">
                  <path d="M4 8.2l2.1 2.1L12 4.7" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
                </svg>
              </span>
              <span class="text-[13px] leading-[1.38] tracking-[-0.01em] text-[#20253A] sm:text-[14px]">
                {{ valuePoints[0] }}
              </span>
            </div>

            <div class="flex items-start gap-2.5 rounded-[18px] border border-white/50 bg-white/70 px-3.5 py-3 shadow-[0_14px_36px_rgba(18,26,52,0.05)] backdrop-blur-sm">
              <span
                aria-hidden="true"
                class="mt-0.5 grid h-6 w-6 shrink-0 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_22px_rgba(89,75,255,0.24)]"
              >
                <svg viewBox="0 0 16 16" class="h-3.5 w-3.5 text-white" fill="none">
                  <path d="M4 8.2l2.1 2.1L12 4.7" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
                </svg>
              </span>
              <span class="text-[13px] leading-[1.38] tracking-[-0.01em] text-[#20253A] sm:text-[14px]">
                {{ valuePoints[1] }}
              </span>
            </div>

            <div class="flex items-start gap-2.5 rounded-[18px] border border-white/50 bg-white/70 px-3.5 py-3 shadow-[0_14px_36px_rgba(18,26,52,0.05)] backdrop-blur-sm">
              <span
                aria-hidden="true"
                class="mt-0.5 grid h-6 w-6 shrink-0 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_22px_rgba(89,75,255,0.24)]"
              >
                <svg viewBox="0 0 16 16" class="h-3.5 w-3.5 text-white" fill="none">
                  <path d="M4 8.2l2.1 2.1L12 4.7" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
                </svg>
              </span>
              <span class="text-[13px] leading-[1.38] tracking-[-0.01em] text-[#20253A] sm:text-[14px]">
                {{ valuePoints[2] }}
              </span>
            </div>

            <div class="flex items-start gap-2.5 rounded-[18px] border border-white/50 bg-white/70 px-3.5 py-3 shadow-[0_14px_36px_rgba(18,26,52,0.05)] backdrop-blur-sm">
              <span
                aria-hidden="true"
                class="mt-0.5 grid h-6 w-6 shrink-0 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_22px_rgba(89,75,255,0.24)]"
              >
                <svg viewBox="0 0 16 16" class="h-3.5 w-3.5 text-white" fill="none">
                  <path d="M4 8.2l2.1 2.1L12 4.7" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
                </svg>
              </span>
              <span class="text-[13px] leading-[1.38] tracking-[-0.01em] text-[#20253A] sm:text-[14px]">
                {{ valuePoints[3] }}
              </span>
            </div>

            <div class="flex items-start gap-2.5 rounded-[18px] border border-white/50 bg-white/70 px-3.5 py-3 shadow-[0_14px_36px_rgba(18,26,52,0.05)] backdrop-blur-sm">
              <span
                aria-hidden="true"
                class="mt-0.5 grid h-6 w-6 shrink-0 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_22px_rgba(89,75,255,0.24)]"
              >
                <svg viewBox="0 0 16 16" class="h-3.5 w-3.5 text-white" fill="none">
                  <path d="M4 8.2l2.1 2.1L12 4.7" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
                </svg>
              </span>
              <span class="text-[13px] leading-[1.38] tracking-[-0.01em] text-[#20253A] sm:text-[14px]">
                {{ valuePoints[4] }}
              </span>
            </div>
          </div>
        </div>

        <!-- RIGHT: Платная основа -->
        <div class="p-4 sm:p-5 lg:p-6">
          <div class="inline-flex items-center gap-2 rounded-full border border-white/50 bg-white/70 px-3 py-1.5 text-[12px] font-semibold text-[#141633]">
            <span class="h-2 w-2 rounded-full bg-[#6F63FF]" aria-hidden="true"></span>
            {{ launchData.rightLabel }}
          </div>

          <div class="mt-4 rounded-[22px] border border-white/50 bg-white/75 p-4 shadow-[0_18px_55px_rgba(18,26,52,0.06)]">
            <div class="flex items-start gap-3">
              <span
                aria-hidden="true"
                class="mt-0.5 grid h-7 w-7 shrink-0 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_12px_26px_rgba(89,75,255,0.24)]"
              >
                <svg viewBox="0 0 16 16" class="h-3.5 w-3.5 text-white" fill="none">
                  <path d="M4 8.2l2.1 2.1L12 4.7" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" />
                </svg>
              </span>

              <div>
                <div class="text-[14px] font-semibold tracking-[-0.02em] text-[#141633] sm:text-[15px]">
                  {{ launchData.paidTitle }}
                </div>
                <div class="mt-1 text-[13px] leading-[1.5] tracking-[-0.01em] text-[#646C89] sm:text-[14px]">
                  {{ launchData.paidDescription }}
                </div>
              </div>
            </div>
          </div>

          <div class="mt-4 rounded-[18px] border border-[#DCDFF3] bg-[linear-gradient(135deg,rgba(111,99,255,0.08)_0%,rgba(126,182,255,0.06)_100%)] p-4 shadow-[0_14px_34px_rgba(92,80,255,0.08)]">
            <div class="text-[13px] font-semibold tracking-[-0.01em] text-[#2D3350]">{{ launchData.noteTitle }}</div>
            <p class="mt-2 text-[12px] leading-[1.45] text-[#5E6685] sm:text-[13px]">
              {{ launchData.noteDescription }}
            </p>
          </div>
        </div>
      </div>
    </div>
    <!-- /2 columns -->
  </div>
</div>

        <!-- 2) Интеграции и аналитика -->
      <!-- 2) Интеграции и аналитика (как на фото) -->
<!-- 2) Интеграции и аналитика (точно как на скрине) -->
<div
  class="relative overflow-hidden rounded-[30px] border border-[#E1E5F2] bg-[linear-gradient(180deg,rgba(255,255,255,0.96)_0%,rgba(246,247,252,0.98)_100%)] p-5 shadow-[0_18px_54px_rgba(18,26,52,0.07)] sm:rounded-[32px] sm:p-6"
>
  <div aria-hidden="true" class="pointer-events-none absolute -right-10 top-0 h-28 w-28 rounded-full bg-[rgba(111,99,255,0.10)] blur-2xl" />
  <div aria-hidden="true" class="pointer-events-none absolute -left-10 bottom-0 h-28 w-28 rounded-full bg-[rgba(126,182,255,0.12)] blur-2xl" />

  <div class="relative">
    <div class="inline-flex items-center gap-2 rounded-full border border-[#E3E8F6] bg-white/85 px-3 py-1.5 text-[11px] font-medium tracking-[-0.01em] text-[#59607D]">
      <span class="h-2 w-2 rounded-full bg-[#7BB3FF]" aria-hidden="true" />
      {{ integrationsData.pill }}
    </div>

    <h4 class="mt-4 text-[20px] font-semibold tracking-[-0.03em] text-[#141633] sm:text-[22px]">
      {{ integrationsData.title }}
    </h4>

    <!-- LIST -->
    <div class="mt-4 overflow-hidden rounded-[22px] border border-[#E4E7F2] bg-[#ECEAF2]/90 shadow-[inset_0_1px_0_rgba(255,255,255,0.7)]">
      <div class="divide-y divide-white/80">
        <div
          v-for="row in integrationsRows"
          :key="row.title"
          class="grid grid-cols-1 gap-3 bg-[#ECEAF2]/95 px-4 py-4 sm:grid-cols-[minmax(210px,1fr)_minmax(260px,1.4fr)_auto] sm:items-center sm:gap-5 sm:px-5"
        >
          <!-- LEFT -->
          <div class="min-w-0">
            <div class="text-[14px] font-semibold tracking-[-0.02em] text-[#141633] sm:text-[15px]">
              {{ row.title }}
            </div>
            <div class="mt-1 text-[12px] leading-[1.45] text-[#8A90A8] sm:hidden">
              {{ row.desc }}
            </div>
          </div>

          <!-- CENTER -->
          <div class="hidden sm:block">
            <div class="text-[12px] leading-[1.45] text-[#8A90A8]">
              {{ row.desc }}
            </div>
          </div>

          <!-- RIGHT -->
          <div class="flex shrink-0 items-center gap-1.5 sm:justify-self-end">
           
            <div class="flex -space-x-2.5">
              <span class="relative z-[2] grid  w-24 place-items-center overflow-hidden border border-white bg-white shadow-[0_10px_24px_rgba(18,26,52,0.12)]">
                <img :src="siteData.assets.images.integrationsBanner" alt="" class="h-full w-full object-contain p-1.5" />
              </span>
           
            </div>

            <!-- plus circle -->
       
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

        <!-- 3) Каналы контакта -->
      <Social_Media />
      </div>
      <!-- /stack -->
    </div>
  </section>
</template>

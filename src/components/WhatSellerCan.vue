<script setup>
import { computed } from 'vue'
import { siteData } from '@/assets/data'

const advantagesData = siteData.advantages
const trainingData = advantagesData.meta.training
const summaryData = advantagesData.meta.summary
const compareRows = advantagesData.items
const checkIcon = advantagesData.media.icon.src

const trainingRows = computed(() => {
  const rows = []
  for (let index = 0; index < trainingData.items.length; index += 2) {
    rows.push(trainingData.items.slice(index, index + 2))
  }
  return rows
})
</script>

<template>
  <section
    id="advantages"
    class="relative z-10 scroll-mt-[92px] bg-[#F3F4F7] pt-0 pb-5 lg:scroll-mt-[104px] lg:pb-6"
  >
    <div class="overflow-x-hidden">
      <div class="mx-auto w-full max-w-[1880px] px-4 sm:px-6 lg:px-10">
        <div class="relative overflow-hidden bg-white">
         
          <!-- ✅ Блок с описанием обучения AI (оставляем) -->
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

      <div
        class="relative grid gap-5 lg:grid-cols-[minmax(0,1.08fr)_minmax(0,0.92fr)] lg:items-start lg:gap-6"
      >
        <!-- LEFT -->
        <div class="text-left">
          <div
            class="inline-flex items-center gap-2 rounded-full border border-[#E3E7F2] bg-white/90 px-2.5 py-2 shadow-[0_10px_24px_rgba(18,26,52,0.05)] backdrop-blur"
          >
            <span
              class="grid h-6 w-6 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_8px_20px_rgba(89,75,255,0.35)]"
            >
              <img
                :src="checkIcon"
                alt=""
                class="h-3.5 w-3.5 brightness-[5] saturate-0"
                aria-hidden="true"
              />
            </span>
            <span class="text-[12px] font-medium tracking-[-0.01em] text-[#2F3452] sm:text-[20px]">
              {{ trainingData.title }}
            </span>
          </div>

          <!-- Сетка источников обучения -->
          <div class="mt-4 space-y-2.5">
            <div v-for="row in trainingRows" :key="row[0].id" class="grid grid-cols-2 gap-2.5">
              <div
                v-for="item in row"
                :key="item.id"
                class="flex w-full items-center justify-center gap-2 rounded-[12px] border border-[#E6EAF4] bg-white/85 px-3 py-2 text-[18px] font-medium text-[#343A57] shadow-[0_8px_20px_rgba(18,26,52,0.04)]"
              >
                <img :src="checkIcon" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
                <span>{{ item.title }}</span>
              </div>
              <div v-if="row.length === 1" aria-hidden="true"></div>
            </div>
          </div>
        </div>

        <!-- RIGHT -->
        <div
          class="relative overflow-hidden rounded-[18px] border border-[#D9DEF0] bg-[#5b6098] p-4 shadow-[0_24px_60px_rgba(18,26,52,0.18)] sm:rounded-[20px] sm:p-5 lg:p-6 text-white"
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
              class="inline-flex items-center gap-2 rounded-full border border-white/10 bg-white/5 px-3 py-1.5 text-[11px] font-medium text-white sm:text-[12px]"
            >
              <span class="h-2 w-2 rounded-full bg-[#78F7C7] shadow-[0_0_14px_rgba(120,247,199,0.8)]" />
              {{ trainingData.meta.rightPill }}
            </div>

            <p
              class="mt-3 text-[15px] font-medium leading-[1.38] tracking-[-0.01em] text-white sm:text-[16px] lg:text-[19px]"
            >
              {{ trainingData.meta.rightTitle }}
            </p>

            <div class="mt-4 grid gap-2.5 sm:gap-3">
              <div
                v-for="bullet in trainingData.meta.rightBullets"
                :key="bullet.id"
                class="flex items-start gap-2.5 text-[12px] leading-[1.35] text-white sm:text-[13px]"
              >
                <img
                  :src="checkIcon"
                  alt=""
                  class="mt-0.5 h-3.5 w-3.5 shrink-0 brightness-[4] saturate-0"
                  aria-hidden="true"
                />
                <span class="text-white">{{ bullet.text }}</span>
              </div>
            </div>
          </div>
        </div>
        <!-- /RIGHT -->
      </div>
    </div>
  </div>

          <!-- ✅ NEW (вариант 4): Summary + раскрытие деталей -->
         
    <div
      class="summary-shell relative overflow-hidden rounded-[26px] border border-[#E6EAF4] bg-[linear-gradient(180deg,#FFFFFF_0%,#F7F8FC_100%)] shadow-[0_30px_90px_rgba(18,26,52,0.12)]"
    >
      <!-- lights -->
      <div
        class="pointer-events-none absolute inset-0 opacity-100"
        style="
          background:
            radial-gradient(42rem 18rem at 12% 0%, rgba(75, 57, 255, 0.11), transparent 62%),
            radial-gradient(36rem 22rem at 100% 70%, rgba(125, 108, 255, 0.10), transparent 64%),
            linear-gradient(180deg, rgba(255,255,255,0.85), rgba(255,255,255,0.0));
        "
        aria-hidden="true"
      />
      <div
        class="pointer-events-none absolute -top-24 left-1/2 h-56 w-[560px] -translate-x-1/2 rounded-full bg-[linear-gradient(90deg,rgba(75,57,255,0.18),rgba(138,125,255,0.10))] blur-3xl"
        aria-hidden="true"
      />

      <div class="relative p-5 sm:p-6 lg:p-8">
        <!-- header row (без кнопки) -->
        <div class="flex flex-col gap-2">
          <div class="text-[14px] font-semibold tracking-[-0.01em] text-[#2F3452] lg:text-[15px]">
            {{ summaryData.subtitle }}
          </div>
          <div
            class="max-w-[980px] text-[16px] font-semibold leading-[1.18] tracking-[-0.03em] text-[#141633] sm:text-[20px] lg:text-[26px]"
          >
            {{ summaryData.title }}

          </div>
        </div>

        <!-- ✅ ОСТАВЛЯЕМ ТОЛЬКО ТО, ЧТО БЫЛО В РАСКРЫВАЮЩЕМСЯ БЛОКЕ -->
        <div
          class="mt-6 overflow-hidden rounded-[22px] border border-[#E6EAF4] bg-white/60 shadow-[0_22px_70px_rgba(18,26,52,0.08)] scroll-mt-[110px]"
        >
          <!-- desktop compare -->
          <div class="hidden lg:block">
            <div class="grid grid-cols-[minmax(240px,0.30fr)_minmax(0,0.35fr)_minmax(0,0.35fr)] px-6 pt-6">
              <div class="text-[14px] font-semibold tracking-[-0.01em] text-[#2F3452]">{{ summaryData.meta.desktopStageLabel }}</div>
              <div class="text-[14px] font-semibold tracking-[-0.01em] text-[#4B39FF]">{{ summaryData.meta.desktopAiLabel }}</div>
              <div class="text-[14px] font-semibold tracking-[-0.01em] text-[#2F3452]">{{ summaryData.meta.desktopHumanLabel }}</div>
            </div>

            <div class="mt-4 divide-y divide-[#E8EBF4]">
              <div
                v-for="r in compareRows"
                :key="r.id"
                class="grid grid-cols-[minmax(240px,0.30fr)_minmax(0,0.35fr)_minmax(0,0.35fr)] px-6 py-6"
              >
                <div>
                  <div class="text-[16px] font-semibold tracking-[-0.02em] text-[#141633]">
                    {{ r.title }}
                  </div>
                  <div class="mt-1 text-[13px] leading-[1.35] text-[#7A809A]">{{ summaryData.meta.stageDescriptionLabel }}</div>
                </div>

                <div>
                  <div
                    class="rounded-[18px] border border-white/40 bg-[linear-gradient(135deg,rgba(75,57,255,0.10)_0%,rgba(138,125,255,0.06)_100%)] p-5 shadow-[0_18px_55px_rgba(89,75,255,0.12)]"
                  >
                    <div class="flex items-start gap-3">
                      <span
                        class="mt-0.5 grid h-7 w-7 shrink-0 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] shadow-[0_10px_22px_rgba(89,75,255,0.24)]"
                        aria-hidden="true"
                      >
                        <span class="text-[14px] text-white">✓</span>
                      </span>
                      <div class="text-[15px] leading-[1.55] tracking-[-0.01em] text-[#141633]">
                        {{ r.aiDescription }}
                      </div>
                    </div>
                  </div>
                </div>

                <div>
                  <div class="rounded-[18px] border border-[#E6EAF4] bg-white/85 p-5 shadow-[0_16px_44px_rgba(18,26,52,0.06)]">
                    <div class="flex items-start gap-3">
                      <span class="mt-0.5 grid h-7 w-7 shrink-0 place-items-center rounded-full bg-[#111827]/5" aria-hidden="true">
                        <span class="text-[14px] font-semibold text-[#2F3452]">—</span>
                      </span>
                      <div class="text-[15px] leading-[1.55] tracking-[-0.01em] text-[#2B2E3A]">
                        {{ r.humanDescription }}
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <div class="px-6 pb-6 pt-1 text-center text-[13px] leading-[1.45] text-[#6B7190]">
              {{ summaryData.meta.desktopFooter }}
            </div>
          </div>

          <!-- mobile compare -->
          <div class="lg:hidden">
            <div class="px-4 pt-5 sm:px-6">
              <div class="text-[14px] font-semibold tracking-[-0.02em] text-[#141633]">{{ summaryData.meta.mobileTitle }}</div>
              <div class="mt-1 text-[13px] leading-[1.45] text-[#616782]">{{ summaryData.meta.mobileSubtitle }}</div>
            </div>

            <div class="mt-4 space-y-4 px-4 pb-6 sm:px-6">
              <div
                v-for="r in compareRows"
                :key="r.id"
                class="rounded-[22px] border border-[#E6EAF4] bg-white/80 p-4 shadow-[0_18px_60px_rgba(18,26,52,0.08)]"
              >
                <div class="text-[15px] font-semibold tracking-[-0.02em] text-[#141633]">
                  {{ r.title }}
                </div>

                <div class="mt-3 grid gap-3">
                  <div
                    class="rounded-[18px] border border-white/40 bg-[linear-gradient(135deg,rgba(75,57,255,0.10)_0%,rgba(138,125,255,0.06)_100%)] p-4 shadow-[0_18px_52px_rgba(89,75,255,0.14)]"
                  >
                    <div class="flex items-center gap-2 text-[12px] font-semibold text-[#4B39FF]">
                      <span class="grid h-6 w-6 place-items-center rounded-full bg-[linear-gradient(135deg,#4B39FF_0%,#8A7DFF_100%)] text-white">
                        ✓
                      </span>
                      {{ summaryData.meta.mobileAiLabel }}
                    </div>
                    <div class="mt-2 text-[14px] leading-[1.55] tracking-[-0.01em] text-[#141633]">
                      {{ r.aiDescription }}
                    </div>
                  </div>

                  <div class="rounded-[18px] border border-[#E6EAF4] bg-white/90 p-4 shadow-[0_14px_44px_rgba(18,26,52,0.06)]">
                    <div class="flex items-center gap-2 text-[12px] font-semibold text-[#2F3452]">
                      <span class="grid h-6 w-6 place-items-center rounded-full bg-[#111827]/5 text-[#2F3452]">
                        —
                      </span>
                      {{ summaryData.meta.mobileHumanLabel }}
                    </div>
                    <div class="mt-2 text-[14px] leading-[1.55] tracking-[-0.01em] text-[#2B2E3A]">
                      {{ r.humanDescription }}
                    </div>
                  </div>
                </div>
              </div>

              <div class="pt-1 text-center text-[13px] leading-[1.45] text-[#6B7190]">
                {{ summaryData.meta.mobileFooter }}
              </div>
            </div>
          </div>
        </div>

        <!-- subtle footer line -->
        
      </div>

      <!-- luxury border -->
      <div class="pointer-events-none absolute inset-0 rounded-[26px]" aria-hidden="true">
        <div class="absolute inset-0 rounded-[26px] border border-white/70 opacity-45"></div>
        <div class="absolute inset-[1px] rounded-[25px] border border-[#E6EAF4] opacity-85"></div>
      </div>
    </div>
  </div>
          <!-- /NEW -->
        </div>
      </div>
    
  </section>
</template>

<style scoped>
.summary-shell {
  background-image:
    radial-gradient(1200px 320px at 50% 0%, rgba(75, 57, 255, 0.06), transparent 60%),
    radial-gradient(900px 280px at 85% 70%, rgba(138, 125, 255, 0.06), transparent 62%),
    linear-gradient(180deg, #ffffff 0%, #f7f8fc 100%);
}

.summary-card--ai {
  position: relative;
}
.summary-card--ai::after {
  content: '';
  position: absolute;
  inset: -1px;
  border-radius: 22px;
  background: radial-gradient(560px 200px at 18% 0%, rgba(75, 57, 255, 0.14), transparent 55%);
  pointer-events: none;
  opacity: 0.55;
}
</style>


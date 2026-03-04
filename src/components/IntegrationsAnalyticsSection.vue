<script setup>
import { computed } from 'vue'
import { siteData } from '@/assets/data'

// Берём блок интеграций из мок-данных
const integrationsData = computed(() => siteData?.aiValue?.meta?.integrations || {})
const integrationsRows = computed(() => integrationsData.value?.items || [])
</script>

<template>
  <section
    id="integrations-analytics"
    class="relative overflow-hidden rounded-[30px] border border-[#E1E5F2] bg-[linear-gradient(180deg,rgba(255,255,255,0.96)_0%,rgba(246,247,252,0.98)_100%)] p-5 shadow-[0_18px_54px_rgba(18,26,52,0.07)] sm:rounded-[32px] sm:p-6"
  >
    <!-- Decorative blobs -->
    <div aria-hidden="true" class="pointer-events-none absolute -right-10 top-0 h-28 w-28 rounded-full bg-[rgba(111,99,255,0.10)] blur-2xl" />
    <div aria-hidden="true" class="pointer-events-none absolute -left-10 bottom-0 h-28 w-28 rounded-full bg-[rgba(126,182,255,0.12)] blur-2xl" />

    <div class="relative">
      <!-- Pill (если есть) -->
      <div
        v-if="integrationsData.subtitle"
        class="inline-flex items-center gap-2 rounded-full border border-[#E3E8F6] bg-white/90 px-3 py-1.5 text-[12px] font-medium tracking-[-0.01em] text-[#4F5672]"
      >
        <span class="h-2 w-2 rounded-full bg-[#7BB3FF]" aria-hidden="true" />
        {{ integrationsData.subtitle }}
      </div>

      <h4 class="mt-3 text-[20px] font-semibold tracking-[-0.03em] text-[#141633] sm:text-[24px]">
        {{ integrationsData.title }}
      </h4>

      <!-- LIST -->
      <div
        class="mt-4 overflow-hidden rounded-[22px] border border-[#E4E7F2] bg-white/70 shadow-[inset_0_1px_0_rgba(255,255,255,0.85)]"
      >
        <div class="divide-y divide-[#E7EAF4]">
          <div
            v-for="row in integrationsRows"
            :key="row.id"
            class="grid grid-cols-1 gap-3 px-4 py-4 sm:grid-cols-[minmax(240px,1fr)_minmax(320px,1.6fr)_auto] sm:items-center sm:gap-6 sm:px-6 sm:py-4"
          >
            <!-- LEFT -->
            <div class="min-w-0">
              <div class="text-[15px] font-semibold tracking-[-0.02em] text-[#141633] sm:text-[16px]">
                {{ row.title }}
              </div>

              <!-- mobile desc -->
              <div class="mt-1 text-[13px] leading-[1.45] text-[#56607A] sm:hidden">
                {{ row.description }}
              </div>
            </div>

            <!-- CENTER (desktop desc) -->
            <div class="hidden sm:block">
              <div class="text-[13px] leading-[1.5] text-[#56607A]">
                {{ row.description }}
              </div>
            </div>

            <!-- RIGHT (icon) -->
            <div class="flex shrink-0 items-center sm:justify-self-end">
              <span
                class="grid h-12 w-[128px] place-items-center overflow-hidden rounded-full border border-[#EEF1FA] bg-white shadow-[0_10px_24px_rgba(18,26,52,0.10)]"
              >
                <img
                  :src="row?.media?.image?.src"
                  :alt="row?.media?.image?.alt || row?.title || ''"
                  class="h-full w-full object-contain p-2"
                  loading="lazy"
                />
              </span>
            </div>
          </div>
        </div>
      </div>

      <!-- optional helper text (если надо) -->
      <!-- <p class="mt-3 text-[12px] text-[#6B7190]">Подключаем данные, каналы и контроль эффективности</p> -->
    </div>
  </section>
</template>
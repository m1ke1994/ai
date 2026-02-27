<script setup>
const contactChannels = [
  'Сайт',
  'Telegram',
  'Avito',
  'Instagram',
  'Facebook',
  'WhatsApp',
  'YouTube',
  'TikTok',
  'Mail',
  'ВКонтакте',
  'Max',
]
</script>

<template>
  <!-- ✅ Контакты / Омниканальность (фон + телефон) -->
  <div
    class="relative overflow-hidden rounded-[30px] border border-[#E1E5F2] bg-[#0b0f2a] p-5 pb-0 shadow-[0_22px_70px_rgba(18,26,52,0.18)] sm:rounded-[32px] sm:p-6 sm:pb-0 lg:p-7 lg:pb-0"
  >
    <!-- background image -->
    <img
      src="/bg-fon.png"
      alt=""
      aria-hidden="true"
      class="pointer-events-none absolute inset-0 h-full w-full object-cover opacity-[0.75]"
      draggable="false"
    />

    <!-- overlays -->
    <div
      aria-hidden="true"
      class="pointer-events-none absolute inset-0 bg-[linear-gradient(180deg,rgba(5,8,26,0.78)_0%,rgba(5,8,26,0.58)_45%,rgba(5,8,26,0.84)_100%)]"
    />
    <div
      aria-hidden="true"
      class="pointer-events-none absolute inset-0 opacity-[0.18]"
      style="
        background-image: repeating-linear-gradient(
          130deg,
          rgba(255, 255, 255, 0.20) 0px,
          rgba(255, 255, 255, 0.20) 1px,
          transparent 1px,
          transparent 16px
        );
      "
    />
    <div aria-hidden="true" class="pointer-events-none absolute -top-16 -right-24 h-64 w-64 rounded-full bg-[#6F63FF]/25 blur-3xl" />
    <div aria-hidden="true" class="pointer-events-none absolute -bottom-20 -left-24 h-64 w-64 rounded-full bg-[#7BB3FF]/20 blur-3xl" />

    <div class="relative grid gap-6 lg:grid-cols-[minmax(0,1.05fr)_minmax(0,0.95fr)] lg:items-center">
      <!-- LEFT: text + channels -->
      <div>
        <div
          class="inline-flex items-center gap-2 rounded-full border border-white/10 bg-white/5 px-3 py-1.5 text-[11px] font-medium tracking-[-0.01em] text-white/80 backdrop-blur"
        >
          <span class="h-2 w-2 rounded-full bg-[#6F63FF] shadow-[0_0_14px_rgba(111,99,255,0.75)]" aria-hidden="true" />
          Омниканальность
        </div>

        <h4 class="mt-4 text-[22px] font-semibold tracking-[-0.03em] text-white sm:text-[26px]">
          Каналы контакта
        </h4>

        <p class="mt-2 max-w-[720px] text-[13px] leading-[1.55] text-white/70 sm:text-[14px]">
          Единая логика ответов и сбор лидов во всех ключевых каналах общения с клиентом.
        </p>

        <div class="mt-5 grid grid-cols-2 gap-2.5 sm:grid-cols-3 lg:grid-cols-4">
          <div
            v-for="channel in contactChannels"
            :key="channel"
            class="group flex min-h-[44px] items-center justify-center gap-2 rounded-[14px] border border-white/10 bg-white/5 px-3 py-2 text-[12px] font-medium tracking-[-0.01em] text-white/90 shadow-[0_10px_24px_rgba(0,0,0,0.18)] backdrop-blur transition hover:-translate-y-0.5 hover:border-white/20 hover:bg-white/8"
          >
            <img
              src="/vecor.svg"
              alt=""
              aria-hidden="true"
              class="h-4 w-4 shrink-0 brightness-[5] saturate-0 opacity-90 transition group-hover:opacity-100"
            />
            <span class="truncate">{{ channel }}</span>
          </div>
        </div>
      </div>

      <!-- RIGHT: phone (без матового контейнера + больше размер + без нижнего отступа) -->
      <div class="relative mx-auto w-full max-w-[620px] self-end">
        <div
          aria-hidden="true"
          class="pointer-events-none absolute -inset-10 rounded-[40px] bg-[radial-gradient(closest-side,rgba(111,99,255,0.22),transparent_70%)] blur-2xl"
        />
        <!-- убрали: border/bg/padding/backdrop-blur -->
        <div class="relative">
          <img
            src="/hiro2.png"
            alt="Превью телефона"
            class="h-auto w-full object-contain translate-y-[6px] sm:translate-y-[10px] lg:translate-y-[14px]"
            draggable="false"
          />
        </div>
      </div>
    </div>
  </div>
</template>
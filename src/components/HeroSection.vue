<script setup>

// hiro.png tuning (size + offsets)
const hiroMobileImageVars = {
  '--hiro-mobile-w': '320px',
  '--hiro-mobile-max-w': '86vw',
  '--hiro-mobile-w-sm': '360px',
  '--hiro-mobile-max-w-sm': '80vw',
}

const hiroDesktopImageVars = {
  '--hiro-desktop-right': '50px',
  '--hiro-desktop-bottom': '-100px',
  '--hiro-desktop-w': '600px',
  '--hiro-desktop-w-xl': '600px',
  '--hiro-desktop-w-2xl': '600px',
}

const heroFloatingBadgesVars = {
  '--hero-badges-left': '2%',
  '--hero-badges-top': '49%',
}
</script>

<template>
  <section class="relative isolate overflow-hidden rounded-none lg:rounded-[40px]">
    <!-- фон -->
    <div
      class="absolute inset-0 z-0 bg-[linear-gradient(180deg,#02030D_0%,#04061A_24%,#0B0F34_58%,#1C225A_100%)]"
      aria-hidden="true"
    />
    <div
      class="absolute inset-0 z-[2] opacity-90"
      style="
        background:
          radial-gradient(38rem 28rem at 34% 36%, rgba(34, 42, 136, 0.22), transparent 70%),
          radial-gradient(34rem 26rem at 63% 49%, rgba(44, 53, 160, 0.22), transparent 72%),
          radial-gradient(28rem 22rem at 100% 88%, rgba(92, 95, 178, 0.2), transparent 72%);
      "
      aria-hidden="true"
    />
    <img
      src="/tilda.png"
      alt=""
      aria-hidden="true"
      class="pointer-events-none absolute bottom-[-250px] left-1/2 z-[1] w-[88%] min-w-[620px] -translate-x-1/2 select-none opacity-5 sm:min-w-[760px]"
    />
    <img
      src="/hiro.png"
      alt="Интерфейс переписки в мессенджере на смартфоне"
      :style="hiroDesktopImageVars"
      class="pointer-events-none absolute right-[var(--hiro-desktop-right)] bottom-[var(--hiro-desktop-bottom)] z-[5] hidden w-[var(--hiro-desktop-w)] max-w-full object-contain select-none lg:block xl:w-[var(--hiro-desktop-w-xl)] xl:max-w-none 2xl:w-[var(--hiro-desktop-w-2xl)]"
      draggable="false"
    />

    <!-- Контент -->
    <div class="relative z-10 mx-auto max-w-[1720px] px-4 sm:px-6 lg:px-10">
      <!-- МОБИЛКА -->
      <div class="relative flex flex-col items-center pt-12 pb-28 text-center lg:hidden">
        <h1
          class="max-w-[360px] text-[30px] font-semibold leading-[1.15] tracking-[-0.03em] text-white sm:max-w-[420px] sm:text-[34px]"
        >
          <span class="block">ИИ отдел продаж</span>
          <span class="block">для вашего бизнеса</span>
        </h1>

        <p class="mt-5 max-w-[340px] text-[14px] leading-[1.5] text-[#A9AEC8] sm:max-w-[420px] sm:text-[15px]">
          Отвечает мгновенно 24/7 на всех языках тысячам клиентов одновременно
        </p>

        <!-- телефон по центру -->
        <div class="mt-7 w-full">
          <img
            src="/hiro.png"
            alt="Интерфейс переписки в мессенджере на смартфоне"
            :style="hiroMobileImageVars"
            class="mx-auto w-[var(--hiro-mobile-w)] max-w-[var(--hiro-mobile-max-w)] object-contain sm:w-[var(--hiro-mobile-w-sm)] sm:max-w-[var(--hiro-mobile-max-w-sm)]"
            draggable="false"
          />
        </div>

        <!-- большая кнопка внизу блока -->
        <div class="absolute bottom-4 left-0 right-0 px-4">
          <div class="mx-auto grid w-full max-w-[520px] grid-cols-3 gap-2 sm:gap-3">
            <div
              class="hero-soft-chip hero-soft-chip--1 flex h-[44px] items-center justify-center gap-1.5 rounded-[14px] border border-white/10 bg-white/5 px-2 text-center text-[12px] font-medium text-white/95 backdrop-blur sm:h-[48px] sm:gap-2 sm:rounded-[16px] sm:px-3 sm:text-[13px]"
            >
              <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
              <span>&#1058;&#1086;&#1095;&#1085;&#1086;</span>
            </div>

            <div
              class="hero-soft-chip hero-soft-chip--2 flex h-[44px] items-center justify-center gap-1.5 rounded-[14px] border border-white/10 bg-white/5 px-2 text-center text-[12px] font-medium text-white/95 backdrop-blur sm:h-[48px] sm:gap-2 sm:rounded-[16px] sm:px-3 sm:text-[13px]"
            >
              <img src="/vecor.svg" alt="" class="h-3.5 w-3.5" aria-hidden="true" />
              <span>&#1041;&#1099;&#1089;&#1090;&#1088;&#1086;</span>
            </div>

            <div
              class="hero-soft-chip hero-soft-chip--3 flex h-[44px] items-center justify-center gap-1.5 rounded-[14px] border border-[#8E84FF]/20 bg-[linear-gradient(90deg,rgba(75,57,255,0.18)_0%,rgba(125,108,255,0.10)_100%)] px-2 text-center text-[12px] font-medium text-white shadow-[0_10px_30px_rgba(89,75,255,0.16)] backdrop-blur sm:h-[48px] sm:gap-2 sm:rounded-[16px] sm:px-3 sm:text-[13px]"
            >
              <img src="/vecor.svg" alt="" class="h-3.5 w-3.5 brightness-200 saturate-0" aria-hidden="true" />
              <span>&#1040;&#1074;&#1090;&#1086;&#1085;&#1086;&#1084;&#1085;&#1086;</span>
            </div>
          </div>
        </div>
      </div>

      <!-- ДЕСКТОП -->
      <div
        class="hidden lg:grid lg:min-h-[680px] lg:grid-cols-[minmax(0,1.03fr)_minmax(0,0.97fr)] lg:items-start lg:gap-4 xl:min-h-[730px] xl:gap-6"
      >
        <!-- левый блок -->
        <div class="relative pt-12 pb-32 xl:pt-20 xl:pb-40 2xl:pt-24 2xl:pb-44">
          <h1
            class="max-w-[620px] text-[48px] font-semibold leading-[1.12] tracking-[-0.03em] text-white xl:max-w-[790px] xl:text-[64px] 2xl:text-[72px]"
          >
            <span class="block">ИИ отдел продаж</span>
            <span class="mt-3 block">для вашего бизнеса</span>
          </h1>

          <p class="mt-6 max-w-[520px] text-[18px] leading-[1.42] text-[#A9AEC8] xl:mt-8 xl:max-w-[650px] xl:text-[22px]">
            Отвечает мгновенно 24/7 на всех языках тысячам клиентов одновременно
          </p>

          <div class="mt-7 hidden max-w-[560px] flex-wrap gap-3 lg:flex xl:mt-8 xl:gap-4">
            <div
              class="hero-soft-chip hero-soft-chip--1 inline-flex items-center gap-2 rounded-[14px] border border-white/10 bg-white/5 px-4 py-2 text-[14px] font-medium text-white/95 backdrop-blur xl:rounded-[16px] xl:px-5 xl:py-2.5 xl:text-[16px]"
            >
              <img src="/vecor.svg" alt="" class="h-4 w-4" aria-hidden="true" />
              <span>&#1058;&#1086;&#1095;&#1085;&#1086;</span>
            </div>

            <div
              class="hero-soft-chip hero-soft-chip--2 inline-flex items-center gap-2 rounded-[14px] border border-white/10 bg-white/5 px-4 py-2 text-[14px] font-medium text-white/95 backdrop-blur xl:rounded-[16px] xl:px-5 xl:py-2.5 xl:text-[16px]"
            >
              <img src="/vecor.svg" alt="" class="h-4 w-4" aria-hidden="true" />
              <span>&#1041;&#1099;&#1089;&#1090;&#1088;&#1086;</span>
            </div>

            <div
              class="hero-soft-chip hero-soft-chip--3 inline-flex items-center gap-2 rounded-[14px] border border-[#8E84FF]/20 bg-[linear-gradient(90deg,rgba(75,57,255,0.18)_0%,rgba(125,108,255,0.10)_100%)] px-4 py-2 text-[14px] font-medium text-white shadow-[0_10px_30px_rgba(89,75,255,0.16)] backdrop-blur xl:rounded-[16px] xl:px-5 xl:py-2.5 xl:text-[16px]"
            >
              <img src="/vecor.svg" alt="" class="h-4 w-4 brightness-200 saturate-0" aria-hidden="true" />
              <span>&#1040;&#1074;&#1090;&#1086;&#1085;&#1086;&#1084;&#1085;&#1086;</span>
            </div>
          </div>

     <!--      <button
            type="button"
            class="mt-8 inline-flex min-h-[72px] items-center justify-center rounded-[20px]
                   bg-[linear-gradient(90deg,#4B39FF_0%,#9E90FF_100%)]
                   px-10 text-[18px] font-medium text-white
                   shadow-[0_20px_60px_rgba(89,75,255,0.28)]
                   transition lg:min-w-[320px]
                   xl:mt-10 xl:min-h-[82px] xl:px-12 xl:text-[20px] xl:min-w-[410px]
                   hover:[background-image:none] hover:bg-white hover:text-black"
          >
            Подключить AI-отдел продаж
          </button> -->

        </div>

        <!-- правый блок -->
        <div class="relative flex min-h-[680px] flex-col justify-end self-end xl:min-h-[730px]">
          <div
            :style="heroFloatingBadgesVars"
            class="pointer-events-none absolute left-[var(--hero-badges-left)] top-[var(--hero-badges-top)] z-[6] hidden -translate-y-1/2 lg:flex lg:flex-col lg:gap-3 xl:gap-4"
            aria-hidden="true"
          >
            <div
              class="hero-float-badge hero-float-badge--1 ml-8 inline-flex w-fit items-center gap-3 whitespace-nowrap rounded-[16px] border border-white/10 bg-[#2A2E58]/88 px-4 py-2.5 text-[15px] font-medium text-white shadow-[0_14px_36px_rgba(0,0,0,0.35)] backdrop-blur xl:ml-12 xl:rounded-[18px] xl:px-5 xl:py-3 xl:text-[18px]"
            >
              <span class="grid h-6 w-6 place-items-center rounded-full border border-emerald-300/30 bg-emerald-300/10 text-[13px] text-emerald-300">&#10003;</span>
              <span>&#1053;&#1077; &#1090;&#1077;&#1088;&#1103;&#1077;&#1090; &#1079;&#1072;&#1103;&#1074;&#1082;&#1080;</span>
            </div>

            <div
              class="hero-float-badge hero-float-badge--2 inline-flex w-fit items-center gap-3 whitespace-nowrap rounded-[16px] border border-white/10 bg-[#2A2E58]/88 px-4 py-2.5 text-[15px] font-medium text-white shadow-[0_14px_36px_rgba(0,0,0,0.35)] backdrop-blur xl:rounded-[18px] xl:px-5 xl:py-3 xl:text-[18px]"
            >
              <span class="grid h-6 w-6 place-items-center rounded-full border border-emerald-300/30 bg-emerald-300/10 text-[13px] text-emerald-300">&#10003;</span>
              <span>&#1056;&#1072;&#1073;&#1086;&#1090;&#1072;&#1077;&#1090; 24/7</span>
            </div>

            <div
              class="hero-float-badge hero-float-badge--3 ml-4 inline-flex w-fit items-center gap-3 whitespace-nowrap rounded-[18px] border border-[#8E84FF]/30 bg-[linear-gradient(90deg,rgba(75,57,255,0.28)_0%,rgba(125,108,255,0.18)_100%)] px-5 py-3 text-[16px] font-medium text-white shadow-[0_20px_50px_rgba(89,75,255,0.28)] backdrop-blur xl:ml-8 xl:rounded-[20px] xl:px-6 xl:py-4 xl:text-[20px]"
            >
              <span class="grid h-6 w-6 place-items-center rounded-full border border-emerald-300/35 bg-emerald-300/12 text-[13px] text-emerald-300">&#10003;</span>
              <span>&#1048;&#1085;&#1090;&#1077;&#1075;&#1088;&#1072;&#1094;&#1080;&#1103; &#1089; CRM</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero-soft-chip {
  animation: hero-chip-drift 7s ease-in-out infinite;
  will-change: transform;
}

.hero-soft-chip--1 {
  animation-delay: 0.15s;
}

.hero-soft-chip--2 {
  animation-delay: 0.85s;
}

.hero-soft-chip--3 {
  animation-delay: 1.55s;
}

.hero-float-badge {
  animation: hero-badge-float 6s ease-in-out infinite;
  will-change: transform;
}

.hero-float-badge--1 {
  animation-delay: 0s;
}

.hero-float-badge--2 {
  animation-delay: 1s;
}

.hero-float-badge--3 {
  animation-delay: 2s;
}

@keyframes hero-badge-float {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }
  50% {
    transform: translate3d(0, -8px, 0);
  }
}

@keyframes hero-chip-drift {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }
  35% {
    transform: translate3d(0, -3px, 0);
  }
  65% {
    transform: translate3d(0, 2px, 0);
  }
}

@media (prefers-reduced-motion: reduce) {
  .hero-soft-chip,
  .hero-float-badge {
    animation: none;
  }
}
</style>

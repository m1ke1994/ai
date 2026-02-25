<script setup>
import HeroLogosStrip from '@/components/HeroLogosStrip.vue'
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

    <!-- Контент -->
    <div class="relative z-10 mx-auto max-w-[1720px] px-4 sm:px-6 lg:px-10">
      <!-- МОБИЛКА (как на скрине) -->
      <div class="relative flex flex-col items-center pt-12 pb-28 text-center lg:hidden">
        <h1 class="max-w-[360px] text-[30px] font-semibold leading-[1.15] tracking-[-0.03em] text-white sm:max-w-[400px] sm:text-[34px]">
          <span class="block">Запустите ИИ-продажника</span>
          <span class="block">для отдела продаж</span>
          <span class="mt-2 block text-[#736CFF]">за 1 день — бесплатно</span>
        </h1>

        <p class="mt-5 max-w-[340px] text-[14px] leading-[1.5] text-[#A9AEC8] sm:max-w-[380px] sm:text-[15px]">
          Он будет квалифицировать заявки 24/7, переводить тёплых лидов менеджерам и
          экономить до 40% времени отдела продаж
        </p>

        <!-- телефон по центру -->
        <div class="mt-7 w-full">
          <img
            src="/hiro.png"
            alt="Интерфейс переписки в мессенджере на смартфоне"
            class="mx-auto w-[320px] max-w-[86vw] object-contain sm:w-[360px] sm:max-w-[80vw]"
            draggable="false"
          />
        </div>

        <!-- большая кнопка внизу блока (как на скрине) -->
        <div class="absolute bottom-4 left-0 right-0 px-4">
          <button
            type="button"
            class="mx-auto flex h-[72px] w-full max-w-[520px] items-center justify-center rounded-[18px]
                   bg-[linear-gradient(90deg,#4B39FF_0%,#9E90FF_100%)]
                   text-[18px] font-medium text-white
                   shadow-[0_20px_60px_rgba(89,75,255,0.28)]
                   transition active:scale-[0.99]"
          >
            Подключить ИИ-продажника
          </button>
        </div>
      </div>

      <!-- ДЕСКТОП (оставляем как сейчас) -->
      <div class="hidden lg:grid lg:min-h-[680px] lg:grid-cols-[minmax(0,1.03fr)_minmax(0,0.97fr)] lg:items-start lg:gap-4 xl:min-h-[730px] xl:gap-6">
        <!-- левый блок -->
        <div class="relative pt-12 pb-32 xl:pt-20 xl:pb-40 2xl:pt-24 2xl:pb-44">
          <h1
            class="max-w-[620px] text-[48px] font-semibold leading-[1.12] tracking-[-0.03em] text-white xl:max-w-[790px] xl:text-[64px] 2xl:text-[72px]"
          >
            <span class="block">Запустите ИИ-продажника</span>
            <span class="mt-3 block">для отдела продаж</span>
            <span class="mt-3 block text-[#736CFF]">за 1 день — бесплатно</span>
          </h1>

          <p class="mt-6 max-w-[520px] text-[18px] leading-[1.42] text-[#A9AEC8] xl:mt-8 xl:max-w-[650px] xl:text-[22px]">
            Он будет квалифицировать заявки 24/7, переводить тёплых лидов менеджерам и
            экономить до 40% времени отдела продаж
          </p>

          <button
            type="button"
            class="mt-8 inline-flex min-h-[72px] items-center justify-center rounded-[20px]
                   bg-[linear-gradient(90deg,#4B39FF_0%,#9E90FF_100%)]
                   px-10 text-[18px] font-medium text-white
                   shadow-[0_20px_60px_rgba(89,75,255,0.28)]
                   transition lg:min-w-[320px]
                   xl:mt-10 xl:min-h-[82px] xl:px-12 xl:text-[20px] xl:min-w-[410px]
                   hover:[background-image:none] hover:bg-white hover:text-black"
          >
            Подключить ИИ-продажника
          </button>

          <!-- на мобилке логотипов нет (как на скрине) -->
          <div class="mt-10">
            <HeroLogosStrip />
          </div>
        </div>

        <!-- правый блок -->
        <div class="relative flex min-h-[680px] flex-col justify-end self-end xl:min-h-[730px]">
          <div
            class="absolute left-[14%] top-[37%] z-20 hidden items-center gap-2 rounded-[16px] border border-white/10 bg-[#2A2E58]/88 px-4 py-2.5 text-[16px] font-medium text-white shadow-[0_14px_36px_rgba(0,0,0,0.35)] backdrop-blur lg:flex xl:rounded-[18px] xl:px-5 xl:py-3 xl:text-[18px]"
          >
            <img src="/vecor.svg" alt="" class="h-4 w-4" aria-hidden="true" />
            <span>Точно</span>
          </div>

          <div
            class="absolute left-[9%] top-[49%] z-20 hidden items-center gap-2 rounded-[16px] border border-white/10 bg-[#2A2E58]/88 px-4 py-2.5 text-[16px] font-medium text-white shadow-[0_14px_36px_rgba(0,0,0,0.35)] backdrop-blur lg:flex xl:rounded-[18px] xl:px-5 xl:py-3 xl:text-[18px]"
          >
            <img src="/vecor.svg" alt="" class="h-4 w-4" aria-hidden="true" />
            <span>Быстро</span>
          </div>

          <div
            class="absolute left-[0%] top-[61%] z-20 hidden items-center gap-2 rounded-[18px] bg-[linear-gradient(90deg,#4B39FF_0%,#7D6CFF_100%)] px-5 py-3 text-[18px] font-medium text-white shadow-[0_20px_50px_rgba(89,75,255,0.42)] lg:flex xl:rounded-[20px] xl:px-6 xl:py-4 xl:text-[20px]"
          >
            <img src="/vecor.svg" alt="" class="h-4 w-4 brightness-200 saturate-0" aria-hidden="true" />
            <span>Автономно</span>
          </div>

          <img
            src="/hiro.png"
            alt="Интерфейс переписки в мессенджере на смартфоне"
            class="absolute bottom-0 right-0 z-[5] w-[620px] max-w-full object-contain xl:w-[780px] xl:max-w-none 2xl:w-[840px]"
            draggable="false"
          />
        </div>
      </div>
    </div>
  </section>
</template>

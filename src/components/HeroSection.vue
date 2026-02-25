<script setup>
const logos = ['/1.svg', '/2.svg', '/3.svg', '/4.svg', '/5.svg']
</script>

<template>
  <section class="relative isolate overflow-hidden bg-[#02030D]">
    <div
      class="absolute inset-0 z-0 bg-[linear-gradient(180deg,#02030D_0%,#04061A_24%,#0B0F34_58%,#1C225A_100%)]"
      aria-hidden="true"
    />

    <img
      src="/tilda.png"
      alt=""
      aria-hidden="true"
      class="pointer-events-none absolute bottom-[-250px] left-1/2 z-[1] w-[88%] min-w-[760px] -translate-x-1/2 select-none opacity-5"
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

    <div class="relative z-10 mx-auto max-w-[1720px] px-4 sm:px-6 lg:px-10">
      <div class="grid items-start gap-6 lg:min-h-[730px] lg:grid-cols-[minmax(0,1.03fr)_minmax(0,0.97fr)]">
        <div class="relative pt-10 pb-10 sm:pt-14 sm:pb-12 lg:pt-20 lg:pb-40 xl:pt-24 xl:pb-44">
          <h1
            class="max-w-[790px] text-[40px] font-semibold leading-[1.12] tracking-[-0.03em] text-white sm:text-[52px] lg:text-[64px] xl:text-[72px]"
          >
            <span class="block">Запустите ИИ-продажника</span>
            <span class="mt-3 block">для отдела продаж</span>
            <span class="mt-3 block text-[#736CFF]">за 1 день — бесплатно</span>
          </h1>

          <p
            class="mt-8 max-w-[650px] text-base leading-[1.45] text-[#A9AEC8] sm:text-lg lg:text-[22px] lg:leading-[1.42]"
          >
            Он будет квалифицировать заявки 24/7, переводить тёплых лидов менеджерам и
            экономить до 40% времени отдела продаж
          </p>

          <button
            type="button"
            class="mt-10 inline-flex min-h-[72px] items-center justify-center rounded-[20px] bg-[linear-gradient(90deg,#4B39FF_0%,#9E90FF_100%)] px-8 text-lg font-medium text-white shadow-[0_20px_60px_rgba(89,75,255,0.28)] transition sm:min-h-[82px] sm:px-12 sm:text-[20px] lg:min-w-[410px] hover:[background-image:none] hover:bg-white hover:text-black"
          >
            Подключить ИИ-продажника
          </button>

          <div class="mt-16 overflow-x-auto pb-1 sm:mt-20 lg:absolute lg:bottom-8 lg:left-0 lg:mt-0 lg:w-[1180px] lg:max-w-none lg:overflow-visible xl:w-[1280px]">
            <div class="flex min-w-max flex-nowrap items-center gap-x-12 whitespace-nowrap opacity-60 grayscale sm:gap-x-14 lg:gap-x-16 xl:gap-x-20">
              <img
                v-for="logo in logos"
                :key="logo"
                :src="logo"
                alt=""
                class="h-9 w-auto shrink-0 object-contain sm:h-10 lg:h-36 xl:h-36"
                loading="lazy"
                aria-hidden="true"
              />
            </div>
          </div>
        </div>

        <div class="relative flex min-h-[360px] flex-col justify-end sm:min-h-[460px] lg:min-h-[730px] lg:self-end">
          <div
            class="absolute left-[14%] top-[37%] z-20 hidden items-center gap-2 rounded-[18px] border border-white/10 bg-[#2A2E58]/88 px-5 py-3 text-[18px] font-medium text-white shadow-[0_14px_36px_rgba(0,0,0,0.35)] backdrop-blur lg:flex"
          >
            <img src="/vecor.svg" alt="" class="h-4 w-4" aria-hidden="true" />
            <span>Точно</span>
          </div>

          <div
            class="absolute left-[9%] top-[49%] z-20 hidden items-center gap-2 rounded-[18px] border border-white/10 bg-[#2A2E58]/88 px-5 py-3 text-[18px] font-medium text-white shadow-[0_14px_36px_rgba(0,0,0,0.35)] backdrop-blur lg:flex"
          >
            <img src="/vecor.svg" alt="" class="h-4 w-4" aria-hidden="true" />
            <span>Быстро</span>
          </div>

          <div
            class="absolute left-[0%] top-[61%] z-20 hidden items-center gap-2 rounded-[20px] bg-[linear-gradient(90deg,#4B39FF_0%,#7D6CFF_100%)] px-6 py-4 text-[20px] font-medium text-white shadow-[0_20px_50px_rgba(89,75,255,0.42)] lg:flex"
          >
            <img src="/vecor.svg" alt="" class="h-4 w-4 brightness-200 saturate-0" aria-hidden="true" />
            <span>Автономно</span>
          </div>

          <img
            src="/hiro.png"
            alt="Интерфейс переписки в мессенджере на смартфоне"
            class="relative z-100 ml-auto mt-4 w-[390px] max-w-none translate-y-[7%] object-contain sm:w-[520px] md:w-[620px] lg:absolute lg:bottom-0 lg:right-0 lg:mt-0 lg:w-[840px] xl:right-0 xl:bottom-0 xl:w-[860px]"
            draggable="false"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const logos = ['/1.svg', '/2.svg', '/3.svg', '/4.svg', '/5.svg', '/6.svg', '/7.svg']
</script>

<template>
  <section class="relative isolate overflow-hidden bg-[#030412]">
    <div
      class="absolute inset-0 bg-[linear-gradient(180deg,#040516_0%,#070925_28%,#11154A_68%,#232860_100%)]"
      aria-hidden="true"
    />
    <div
      class="absolute inset-0 opacity-90"
      style="
        background:
          radial-gradient(42rem 42rem at 54% 37%, rgba(26, 32, 112, 0.32), transparent 64%),
          radial-gradient(32rem 32rem at 36% 88%, rgba(53, 61, 155, 0.28), transparent 64%),
          radial-gradient(26rem 26rem at 99% 92%, rgba(93, 98, 190, 0.22), transparent 64%);
      "
      aria-hidden="true"
    />

    <div class="pointer-events-none absolute left-[43%] top-[22%] hidden h-[460px] w-[460px] rounded-full bg-[#1B2067]/30 lg:block" aria-hidden="true" />
    <div class="pointer-events-none absolute left-[29%] top-[69%] hidden h-[360px] w-[360px] rounded-full bg-[#2A2F7D]/22 lg:block" aria-hidden="true" />
    <div class="pointer-events-none absolute right-[-120px] bottom-[-180px] hidden h-[520px] w-[520px] rounded-full bg-[#4D52AA]/18 lg:block" aria-hidden="true" />

    <div class="relative mx-auto max-w-[1720px] px-4 sm:px-6 lg:px-10">
      <div class="grid min-h-[calc(100vh-64px)] items-start gap-8 lg:grid-cols-[minmax(0,1.03fr)_minmax(0,0.97fr)]">
        <div class="pt-10 pb-12 sm:pt-14 lg:pt-20 lg:pb-16 xl:pt-24">
          <h1 class="max-w-[780px] text-[40px] font-semibold leading-[1.12] tracking-[-0.03em] text-white sm:text-[52px] lg:text-[64px] xl:text-[72px]">
            <span class="block">Запустите ИИ-продажника</span>
            <span class="mt-3 block">для отдела продаж</span>
            <span class="mt-3 block text-[#736CFF]">за 1 день — бесплатно</span>
          </h1>

          <p class="mt-8 max-w-[650px] text-base leading-[1.45] text-[#A9AEC8] sm:text-lg lg:text-[22px] lg:leading-[1.42]">
            Он будет квалифицировать заявки 24/7, переводить тёплых лидов менеджерам и
            экономить до 40% времени отдела продаж
          </p>

          <button
            type="button"
            class="mt-10 inline-flex min-h-[72px] items-center justify-center rounded-[20px] bg-[linear-gradient(90deg,#4B39FF_0%,#9E90FF_100%)] px-8 text-lg font-medium text-white shadow-[0_20px_60px_rgba(89,75,255,0.28)] transition hover:brightness-105 sm:min-h-[82px] sm:px-12 sm:text-[20px] lg:min-w-[410px]"
          >
            Подключить ИИ-продажника
          </button>

          <div class="mt-12 sm:mt-16 lg:mt-24">
            <div class="flex flex-wrap items-center gap-x-7 gap-y-5 opacity-60 grayscale">
              <img
                v-for="logo in logos"
                :key="logo"
                :src="logo"
                alt=""
                class="h-7 w-auto object-contain sm:h-8 lg:h-9"
                loading="lazy"
                aria-hidden="true"
              />
            </div>
          </div>
        </div>

        <div class="relative min-h-[360px] pb-6 sm:min-h-[460px] lg:min-h-[780px] lg:pb-0">
          <div class="absolute left-[2%] top-[31%] z-20 hidden lg:flex items-center gap-2 rounded-[18px] border border-white/10 bg-[#262A53]/85 px-5 py-3 text-[18px] font-medium text-white shadow-[0_14px_36px_rgba(0,0,0,0.35)] backdrop-blur">
            <img src="/vecor.svg" alt="" class="h-4 w-4" aria-hidden="true" />
            <span>Точно</span>
          </div>

          <div class="absolute left-[-1%] top-[43%] z-20 hidden lg:flex items-center gap-2 rounded-[18px] border border-white/10 bg-[#262A53]/85 px-5 py-3 text-[18px] font-medium text-white shadow-[0_14px_36px_rgba(0,0,0,0.35)] backdrop-blur">
            <img src="/vecor.svg" alt="" class="h-4 w-4" aria-hidden="true" />
            <span>Быстро</span>
          </div>

          <div class="absolute left-[-8%] top-[56%] z-20 hidden lg:flex items-center gap-2 rounded-[20px] bg-[linear-gradient(90deg,#4B39FF_0%,#7D6CFF_100%)] px-6 py-4 text-[20px] font-medium text-white shadow-[0_20px_50px_rgba(89,75,255,0.42)]">
            <img src="/vecor.svg" alt="" class="h-4 w-4 brightness-200 saturate-0" aria-hidden="true" />
            <span>Автономно</span>
          </div>

          <img
            src="/hiro.png"
            alt="Интерфейс переписки в мессенджере на смартфоне"
            class="relative z-10 ml-auto mt-4 w-[360px] max-w-full object-contain sm:w-[470px] md:w-[560px] lg:absolute lg:bottom-[-92px] lg:right-[-70px] lg:mt-0 lg:w-[760px] xl:right-[-48px] xl:w-[820px]"
            draggable="false"
          />
        </div>
      </div>
    </div>
  </section>
</template>

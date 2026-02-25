<template>
  <section class="bg-[#01020a]">
    <!-- ===================== -->
    <!-- MOBILE -->
    <!-- ===================== -->
    <div class="relative mx-auto overflow-hidden rounded-none lg:hidden">
      <div class="relative h-[760px] w-full overflow-hidden">
        <!-- БАЗОВЫЙ фон -->
        <img
          src="/bg-fon.png"
          alt=""
          aria-hidden="true"
          class="absolute inset-0 h-full w-full object-cover pointer-events-none select-none"
          draggable="false"
        />

        <!-- КАРТИНКА (с телефоном) НА ВСЮ СЕКЦИЮ -->
        <img
          src="/hiro2.png"
          alt="Смартфон с перепиской клиента"
          class="absolute inset-0 z-10 h-full w-full object-cover pointer-events-none select-none"
          draggable="false"
        />

        <!-- Градиент поверх (чтобы текст читался) -->
        <div
          class="absolute inset-0 z-20"
          style="
            background:
              radial-gradient(28rem 18rem at 50% 90%, rgba(109, 84, 255, 0.28), transparent 70%),
              radial-gradient(26rem 16rem at 50% 72%, rgba(84, 71, 236, 0.18), transparent 72%),
              linear-gradient(180deg, rgba(0,0,0,0.58) 0%, rgba(2,4,20,0.62) 46%, rgba(3,4,18,0.78) 100%);
          "
          aria-hidden="true"
        />

        <!-- Диагональная текстура -->
        <div
          class="absolute inset-0 z-20 opacity-[0.18]"
          style="
            background-image: repeating-linear-gradient(
              125deg,
              rgba(174, 181, 255, 0.11) 0px,
              rgba(174, 181, 255, 0.11) 2px,
              transparent 2px,
              transparent 16px
            );
          "
          aria-hidden="true"
        />

        <!-- Верхний текст -->
        <p
          class="absolute inset-x-0 top-[84px] z-30 mx-auto max-w-[320px] px-5 text-center
                 text-[14px] font-normal leading-[1.45] tracking-[-0.02em] text-white/90"
        >
          После работы с нами, среднее время<br />
          ответа клиентам становится 7 секунд
        </p>

        <!-- КНОПКА снизу -->
        <div class="absolute bottom-[18px] left-0 right-0 z-40 px-5">
          <button
            class="flex h-[74px] w-full items-center justify-center rounded-[18px]
                   border border-white/30 bg-white/10 text-[16px] font-medium text-white
                   backdrop-blur-md shadow-[0_18px_60px_rgba(0,0,0,0.38)]
                   transition hover:bg-white/15 active:scale-[0.99]"
          >
            Начать работу
          </button>
        </div>
      </div>
    </div>

    <!-- ===================== -->
    <!-- DESKTOP (как было) -->
    <!-- ===================== -->
    <div class="hidden lg:block">
      <div class="overflow-x-auto">
        <div class="relative mx-auto h-[792px] min-w-[1860px] overflow-hidden rounded-none sm:rounded-[40px]">
          <img
            src="/bg-fon.png"
            alt=""
            aria-hidden="true"
            class="absolute inset-0 h-full w-full object-cover pointer-events-none select-none"
            draggable="false"
          />

          <div
            class="absolute inset-0"
            style="
              background:
                radial-gradient(56rem 22rem at 50% 92%, rgba(109, 84, 255, 0.28), transparent 72%),
                radial-gradient(44rem 18rem at 50% 78%, rgba(84, 71, 236, 0.18), transparent 74%),
                linear-gradient(180deg, rgba(6,10,50,0.85) 0%, rgba(6,10,52,0.85) 42%, rgba(9,10,59,0.9) 100%);
            "
            aria-hidden="true"
          ></div>

          <div
            class="absolute inset-0 opacity-[0.28]"
            style="
              background-image: repeating-linear-gradient(
                125deg,
                rgba(174, 181, 255, 0.11) 0px,
                rgba(174, 181, 255, 0.11) 2px,
                transparent 2px,
                transparent 16px
              );
            "
            aria-hidden="true"
          ></div>

          <p
            class="absolute inset-x-0 top-[78px] z-30 mx-auto max-w-[820px] text-center
                   text-[22px] font-normal leading-[1.35] tracking-[-0.02em] text-white"
          >
            После работы с нами, среднее время ответа<br />
            клиентам становится 7 секунд
          </p>

          <div class="pointer-events-none absolute inset-x-0 top-[318px] z-10 select-none text-center">
            <div class="text-[112px] font-semibold leading-[0.95] tracking-[-0.05em] text-white">
              АВТОМАТИЗАЦИЯ
            </div>
            <div class="mt-8 text-[112px] font-semibold leading-[0.95] tracking-[-0.05em] text-white">
              ВАШЕГО БИЗНЕСА
            </div>
          </div>

          <img
            src="/hiro2.png"
            alt="Смартфон с перепиской клиента"
            class="pointer-events-none absolute bottom-0 left-1/2 z-20 w-[950px] -translate-x-1/2 select-none"
            draggable="false"
          />

          <div class="absolute bottom-[40px] left-1/2 z-30 -translate-x-1/2">
            <button
              class="rounded-[16px] border border-white/40 bg-white/10 px-10 py-4
                     text-lg font-medium text-white backdrop-blur-md
                     transition duration-300 hover:bg-white/20"
            >
              Начать работу
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

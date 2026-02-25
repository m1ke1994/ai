<template>
  <section class="bg-[#01020a] ">
    <div class="overflow-x-auto">
      
      <!-- Основной контейнер -->
      <div
        class="relative mx-auto h-[792px] min-w-[1860px] overflow-hidden rounded-[40px]"
      >

        <!-- Фоновое изображение НА ВСЮ секцию -->
        <img
          src="/bg-fon.png"
          alt=""
          aria-hidden="true"
          class="absolute inset-0 w-full h-full object-cover pointer-events-none select-none"
          draggable="false"
        />

        <!-- Градиент поверх фона -->
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

        <!-- Диагональная текстура -->
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

        <!-- Верхний текст -->
        <p
          class="absolute inset-x-0 top-[78px] z-30 mx-auto max-w-[820px] text-center text-[22px] font-normal leading-[1.35] tracking-[-0.02em] text-white"
        >
          После работы с нами, среднее время ответа<br />
          клиентам становится 7 секунд
        </p>

        <!-- Большой заголовок -->
        <div
          class="pointer-events-none absolute inset-x-0 top-[318px] z-10 select-none text-center"
        >
          <div class="text-[112px] font-semibold leading-[0.95] tracking-[-0.05em] text-white">
            АВТОМАТИЗАЦИЯ
          </div>
          <div class="mt-8 text-[112px] font-semibold leading-[0.95] tracking-[-0.05em] text-white">
            ВАШЕГО БИЗНЕСА
          </div>
        </div>

        <!-- Смартфон -->
        <img
          src="/hiro2.png"
          alt="Смартфон с перепиской клиента"
          class="pointer-events-none absolute bottom-0 left-1/2 z-20 w-[950px] -translate-x-1/2 select-none"
          draggable="false"
        />

        <!-- КНОПКА -->
        <div class="absolute bottom-[40px] left-1/2 z-30 -translate-x-1/2">
          <button
            class="px-10 py-4 rounded-[16px] text-white text-lg font-medium
                   border border-white/40
                   bg-white/10 backdrop-blur-md
                   hover:bg-white/20 transition duration-300"
          >
            Начать работу
          </button>
        </div>

      </div>
    </div>
  </section>
</template>
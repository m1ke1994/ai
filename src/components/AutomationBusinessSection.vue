<script setup>
const CONTACT_FORM_OPEN_EVENT = 'contact-feedback-form:open'

const openContactFormModal = () => {
  if (typeof window === 'undefined') return
  window.dispatchEvent(new CustomEvent(CONTACT_FORM_OPEN_EVENT))
}
</script>

<template>
  <section class="bg-[#01020a]">
    <div class="relative mx-auto overflow-hidden rounded-none lg:hidden">
      <div class="relative h-[760px] w-full overflow-hidden">
        <img
          src="/bg-fon.png"
          alt=""
          aria-hidden="true"
          class="pointer-events-none absolute inset-0 h-full w-full select-none object-cover"
          draggable="false"
        />

        <img
          src="/hiro2.png"
          alt="Смартфон с перепиской клиента"
          class="pointer-events-none absolute inset-0 z-10 h-full w-full select-none object-cover"
          draggable="false"
        />

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

        <p
          class="pointer-events-none absolute inset-x-0 top-[72px] z-30 px-6 text-center text-[13px] font-normal leading-[1.35] tracking-[-0.02em] text-white/90 sm:top-[88px] sm:px-10 sm:text-[15px] md:px-16 md:text-[18px]"
        >
          После работы с нами, среднее время ответа<br />
          клиентам становится 7 секунд
        </p>

        <div class="pointer-events-none absolute inset-x-0 top-1/2 z-30 -translate-y-1/2 px-5 text-center">
          <p
            class="mx-auto max-w-[430px] text-[44px] font-semibold leading-[0.9] tracking-[-0.08em] text-white sm:max-w-[520px] sm:text-[52px] md:max-w-[620px] md:text-[64px]"
          >
            АВТОМАТИЗАЦИЯ<br />
            ВАШЕГО БИЗНЕСА
          </p>
        </div>

        <div class="absolute bottom-[18px] left-0 right-0 z-40 px-5">
          <button
            class="flex h-[74px] w-full items-center justify-center rounded-[18px] border border-white/30 bg-white/10 text-[16px] font-medium text-white shadow-[0_18px_60px_rgba(0,0,0,0.38)] backdrop-blur-md transition hover:bg-white/15 active:scale-[0.99]"
            @click="openContactFormModal"
          >
            Оставить заявку
          </button>
        </div>
      </div>
    </div>

    <div class="hidden lg:block">
      <div class="overflow-x-visible">
        <div class="relative mx-auto h-[620px] w-full max-w-[1860px] overflow-hidden rounded-none sm:rounded-[40px] xl:h-[700px] 2xl:h-[792px]">
          <img
            src="/bg-fon.png"
            alt=""
            aria-hidden="true"
            class="pointer-events-none absolute inset-0 h-full w-full select-none object-cover"
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
            class="absolute inset-x-0 top-[52px] z-30 mx-auto max-w-[620px] px-6 text-center text-[16px] font-normal leading-[1.35] tracking-[-0.02em] text-white xl:top-[64px] xl:max-w-[760px] xl:text-[18px] 2xl:top-[78px] 2xl:max-w-[820px] 2xl:px-0 2xl:text-[22px]"
          >
            После работы с нами, среднее время ответа<br />
            клиентам становится 7 секунд
          </p>

          <div class="pointer-events-none absolute inset-x-0 top-[220px] z-10 select-none text-center xl:top-[270px] 2xl:top-[318px]">
            <div class="text-[70px] font-semibold leading-[0.95] tracking-[-0.05em] text-white xl:text-[88px] 2xl:text-[112px]">
              АВТОМАТИЗАЦИЯ
            </div>
            <div class="mt-5 text-[70px] font-semibold leading-[0.95] tracking-[-0.05em] text-white xl:mt-6 xl:text-[88px] 2xl:mt-8 2xl:text-[112px]">
              ВАШЕГО БИЗНЕСА
            </div>
          </div>

          <img
            src="/hiro2.png"
            alt="Смартфон с перепиской клиента"
            class="pointer-events-none absolute bottom-0 left-1/2 z-20 w-[620px] max-w-full -translate-x-1/2 select-none xl:w-[760px] xl:max-w-none 2xl:w-[950px]"
            draggable="false"
          />

          <div class="absolute bottom-[24px] left-1/2 z-30 -translate-x-1/2 xl:bottom-[32px] 2xl:bottom-[40px]">
            <button
              class="rounded-[16px] border border-white/40 bg-white/10 px-8 py-3 text-base font-medium text-white backdrop-blur-md transition duration-300 hover:bg-white/20 xl:px-9 xl:py-3.5 xl:text-lg 2xl:px-10 2xl:py-4"
              @click="openContactFormModal"
            >
              Начать работу
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { siteData } from '@/assets/data'

const CONTACT_FORM_OPEN_EVENT = siteData.events.contactFormOpen
const integrationStepsData = siteData.integrationSteps
const integrationSteps = integrationStepsData.steps
const ctaTitleLines = integrationStepsData.ctaTitle.split('\n')

const openContactFormModal = () => {
  if (typeof window !== 'undefined') {
    window.dispatchEvent(new Event(CONTACT_FORM_OPEN_EVENT))
  }
}
</script>

<template>
  <section
    id="steps"
    class="relative isolate scroll-mt-[92px] bg-[#F3F4F7] pt-0 pb-8 sm:pt-0 sm:pb-10 lg:scroll-mt-[104px] lg:pt-0 lg:pb-12"
  >
    <!-- Заголовок -->
    <div class="text-center px-4">
      <h2
        class="text-[30px] font-semibold tracking-[-0.02em] !text-black sm:text-[34px] md:text-[40px] lg:text-[42px] xl:text-[48px]"
      >
        {{ integrationStepsData.title }}
      </h2>
      <h3
        class="mt-3 text-[30px] font-semibold tracking-[-0.02em] !text-gray-400 sm:text-[34px] md:text-[40px] lg:mt-4 lg:text-[42px] xl:text-[48px]"
      >
        {{ integrationStepsData.subtitle }}
      </h3>
    </div>

    <div class="mx-auto mt-10 max-w-[1320px] px-4 sm:mt-14 sm:px-6 lg:mt-20 lg:px-8 xl:px-4">
      <!-- МОБИЛКА: колонка -->
      <div class="flex flex-col gap-4 lg:hidden">
        <div
          v-for="(step, index) in integrationSteps"
          :key="index"
          class="relative flex min-h-[420px] flex-col justify-between rounded-[26px] bg-[#E9EBF2] p-6"
        >
          <!-- Текст -->
          <div>
            <p class="text-[15px] !text-gray-500 sm:text-lg">
              {{ step.day }}
            </p>

            <h4 class="mt-2 text-[20px] font-semibold leading-tight !text-black sm:mt-3 sm:text-2xl">
              {{ step.title }}
            </h4>

            <p class="mt-3 text-[15px] leading-relaxed !text-gray-500 sm:mt-4 sm:text-base">
              {{ step.desc }}
            </p>
          </div>

          <!-- Изображение -->
          <div class="mt-5 flex h-[190px] items-center justify-center">
            <img
              v-if="step.image"
              :src="step.image"
              alt=""
              class="max-h-[190px] w-auto object-contain"
              loading="lazy"
              draggable="false"
            />
          </div>
        </div>

        <!-- CTA карточка последней в колонке -->
        <div class="relative overflow-hidden rounded-[26px] bg-[#1B1730] p-6">
          <img
            :src="siteData.assets.images.ctaBackground"
            alt=""
            aria-hidden="true"
            class="pointer-events-none absolute inset-0 h-full w-full object-cover"
            draggable="false"
          />
          <div
            aria-hidden="true"
            class="absolute inset-0 bg-[linear-gradient(180deg,rgba(20,16,34,0.35)_0%,rgba(44,31,85,0.52)_50%,rgba(74,56,145,0.78)_100%)]"
          ></div>

          <div class="relative z-10">
            <h4
              class="text-[28px] font-semibold leading-[0.98] tracking-[-0.03em] text-white sm:text-[34px]"
            >
              {{ ctaTitleLines[0] }}<br />
              {{ ctaTitleLines[1] }}
            </h4>
          </div>

          <button
            type="button"
            class="relative z-10 mt-6 inline-flex h-[56px] w-full items-center justify-center rounded-[16px]
                   border border-white/60 bg-white/10 text-[18px] font-medium tracking-[-0.01em] text-white
                   backdrop-blur-md transition hover:bg-white/20 active:scale-[0.99]"
            @click="openContactFormModal"
          >
            {{ integrationStepsData.ctaButtonLabel }}
          </button>
        </div>
      </div>

      <!-- ДЕСКТОП: как было (2 ряда по 3 колонки) -->
      <div class="hidden lg:block">
        <!-- Первая строка -->
        <div class="grid grid-cols-2 gap-6 xl:grid-cols-3 xl:gap-10">
          <div
            v-for="(step, index) in integrationSteps.slice(0, 3)"
            :key="index"
            class="relative flex min-h-[520px] flex-col justify-between rounded-[32px] bg-[#E9EBF2] p-8 xl:h-[520px] xl:p-10"
          >
            <div>
              <p class="text-base !text-gray-500 xl:text-lg">
                {{ step.day }}
              </p>

              <h4 class="mt-3 text-[22px] font-semibold leading-tight !text-black xl:text-2xl">
                {{ step.title }}
              </h4>

              <p class="mt-4 leading-relaxed !text-gray-500">
                {{ step.desc }}
              </p>
            </div>

            <div class="mt-6 flex h-[190px] items-center justify-center xl:h-[220px]">
              <img
                v-if="step.image"
                :src="step.image"
                alt=""
                class="max-h-[220px] w-auto object-contain"
                loading="lazy"
                draggable="false"
              />
            </div>
          </div>
        </div>

        <!-- Вторая строка -->
        <div class="mt-10 grid grid-cols-2 gap-6 xl:grid-cols-3 xl:gap-10">
          <div
            v-for="(step, index) in integrationSteps.slice(3, 5)"
            :key="index"
            class="relative flex min-h-[520px] flex-col justify-between rounded-[32px] bg-[#E9EBF2] p-8 xl:h-[520px] xl:p-10"
          >
            <div>
              <p class="text-base !text-gray-500 xl:text-lg">
                {{ step.day }}
              </p>

              <h4 class="mt-3 text-[22px] font-semibold leading-tight !text-black xl:text-2xl">
                {{ step.title }}
              </h4>

              <p class="mt-4 leading-relaxed !text-gray-500">
                {{ step.desc }}
              </p>
            </div>

            <div class="mt-6 flex h-[190px] items-center justify-center xl:h-[220px]">
              <img
                v-if="step.image"
                :src="step.image"
                alt=""
                class="max-h-[220px] w-auto object-contain"
                loading="lazy"
                draggable="false"
              />
            </div>
          </div>

          <!-- CTA -->
          <div
            class="relative flex min-h-[520px] flex-col justify-between overflow-hidden rounded-[32px] bg-[#1B1730] p-8 xl:h-[520px] xl:p-10"
          >
            <img
              :src="siteData.assets.images.ctaBackground"
              alt=""
              aria-hidden="true"
              class="pointer-events-none absolute inset-0 h-full w-full object-cover"
              draggable="false"
            />
            <div
              aria-hidden="true"
              class="absolute inset-0 bg-[linear-gradient(180deg,rgba(20,16,34,0.35)_0%,rgba(44,31,85,0.52)_50%,rgba(74,56,145,0.78)_100%)]"
            ></div>

            <div class="relative z-10">
              <h4 class="text-[30px] font-semibold leading-[0.96] tracking-[-0.03em] text-white xl:text-[40px]">
                {{ ctaTitleLines[0] }}<br />
                {{ ctaTitleLines[1] }}
              </h4>
            </div>

            <button
              type="button"
              class="relative z-10 inline-flex h-[56px] w-full items-center justify-center rounded-[16px]
                     border border-white/60 bg-white/10 text-[18px] font-medium tracking-[-0.01em] text-white
                     backdrop-blur-md transition hover:bg-white/20 xl:w-[230px]"
              @click="openContactFormModal"
            >
              {{ integrationStepsData.ctaButtonLabel }}
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

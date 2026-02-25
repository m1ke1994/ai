<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  visualTop: {
    type: Boolean,
    default: false,
  },
})
</script>

<template>
  <div
    class="w-full rounded-[22px] bg-[#EDECF6] px-4 py-4 sm:px-6 sm:py-5
           lg:min-w-[1680px] lg:rounded-[30px] lg:px-[88px] lg:py-[18px]"
  >
    <div
      class="flex flex-col gap-4
             lg:min-h-[174px] lg:flex-row lg:items-center lg:gap-0"
    >
      <!-- Title -->
      <div class="w-full lg:w-[460px] lg:shrink-0">
        <h4
          class="text-[22px] font-medium leading-[1.15] tracking-[-0.02em] text-[#090A12]
                 sm:text-[26px]
                 lg:text-[34px] lg:leading-[1.1]"
        >
          {{ title }}
        </h4>
      </div>

      <!-- Divider (desktop only) -->
      <div class="hidden lg:mx-[72px] lg:block lg:h-[118px] lg:w-px lg:shrink-0 lg:bg-[#D6D7E5]" />

      <!-- Description -->
      <p
        class="w-full whitespace-pre-line text-[15px] leading-[1.45] tracking-[-0.01em] text-[#666A7C]
               sm:text-[16px]
               lg:max-w-[560px] lg:flex-1 lg:text-[24px] lg:leading-[1.26]"
      >
        {{ description }}
      </p>

      <!-- Visual -->
      <div
        class="w-full pt-2"
        :class="[
          visualTop ? 'items-start' : 'items-center',
          'flex justify-center lg:ml-[60px] lg:w-[520px] lg:shrink-0 lg:justify-end lg:pt-0',
        ]"
      >
        <slot />
      </div>
    </div>
  </div>
</template>
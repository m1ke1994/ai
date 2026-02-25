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
  <div class="min-w-[1680px] rounded-[30px] bg-[#EDECF6] px-[88px] py-[18px]">
    <div class="flex min-h-[174px] items-center gap-0">
      <div class="w-[460px] shrink-0">
        <h4 class="text-[34px] font-medium leading-[1.1] tracking-[-0.02em] text-[#090A12]">
          {{ title }}
        </h4>
      </div>

      <div class="mx-[72px] h-[118px] w-px shrink-0 bg-[#D6D7E5]" />

      <p class="max-w-[560px] flex-1 whitespace-pre-line text-[24px] leading-[1.26] tracking-[-0.01em] text-[#666A7C]">
        {{ description }}
      </p>

      <div
        class="ml-[60px] flex w-[520px] shrink-0 justify-end"
        :class="visualTop ? 'items-start' : 'items-center'"
      >
        <slot />
      </div>
    </div>
  </div>
</template>

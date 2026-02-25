<script setup>
defineProps({
  title: { type: String, required: true },
  description: { type: String, required: true },
  visualTop: { type: Boolean, default: false },
})
</script>

<template>
  <div
    class="w-full max-w-full rounded-[22px] bg-[#EDECF6]
           px-4 py-4 sm:px-6 sm:py-5
           lg:rounded-[30px] lg:px-8 lg:py-4
           xl:px-12 xl:py-[18px]
           2xl:px-[88px]"
  >
    <!-- На lg+ делаем justify-between, чтобы блоки равномерно разъехались -->
    <div
      class="flex flex-col gap-4
             lg:min-h-[150px] lg:flex-row lg:items-center lg:justify-between lg:gap-0
             xl:min-h-[174px]"
    >
      <!-- Title -->
      <div class="w-full min-w-0 lg:w-[28%] lg:shrink-0 xl:w-[30%] 2xl:w-[460px]">
        <h4
          class="text-[22px] font-medium leading-[1.15] tracking-[-0.02em] text-[#090A12]
                 sm:text-[26px]
                 lg:text-[26px] lg:leading-[1.1]
                 xl:text-[30px]
                 2xl:text-[34px]"
        >
          {{ title }}
        </h4>
      </div>

      <!-- Divider (desktop only) -->
      <div
        class="hidden lg:block lg:shrink-0 lg:bg-[#D6D7E5]
               lg:h-[90px] lg:w-px
               xl:h-[104px]
               2xl:h-[118px]"
      />

      <!-- Description -->
      <p
        class="w-full min-w-0 whitespace-pre-line text-[15px] leading-[1.45] tracking-[-0.01em] text-[#666A7C]
               sm:text-[16px]
               lg:flex-1 lg:text-[18px] lg:leading-[1.26]
               xl:text-[20px]
               2xl:text-[24px]"
      >
        {{ description }}
      </p>

      <!-- Visual -->
      <div
        class="w-full pt-2"
        :class="[
          visualTop ? 'items-start' : 'items-center',
          // важно: убираем ml-*, потому что он и сдвигал правый блок влево
          'flex justify-center lg:pt-0 lg:shrink-0 lg:justify-end',
          'lg:w-[24%]',
          'xl:w-[28%]',
          '2xl:w-[520px]',
        ]"
      >
        <div class="w-full max-w-full overflow-hidden">
          <slot />
        </div>
      </div>
    </div>
  </div>
</template>
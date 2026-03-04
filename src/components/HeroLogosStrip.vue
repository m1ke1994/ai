<script setup>
import { siteData } from '@/assets/data'

const logos = siteData.heroLogos.items
</script>

<template>
  <div
    class="mx-auto max-w-full touch-pan-x overflow-x-auto bg-[#02030D] pb-2 lg:w-[980px] xl:w-[1180px] 2xl:w-[1280px]"
    style="-webkit-overflow-scrolling: touch;"
  >
    <div class="flex min-w-max flex-nowrap items-center gap-x-12 whitespace-nowrap px-4 opacity-60 grayscale sm:gap-x-14 sm:px-6 lg:gap-x-16 lg:px-0 xl:gap-x-20">
      <img
        v-for="logo in logos"
        :key="logo.id"
        :src="logo.src"
        :alt="logo.alt"
        class="h-9 w-auto shrink-0 object-contain sm:h-10 lg:h-36 xl:h-36"
        loading="lazy"
        aria-hidden="true"
      />
    </div>
  </div>
</template>

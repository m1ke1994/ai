<script setup>
import { siteData } from '@/assets/data'

const logos = siteData.heroLogos.logos
</script>

<template>
  <div class="mt-16 max-w-full overflow-x-auto pb-1 sm:mt-20 lg:absolute lg:bottom-8 lg:left-0 lg:mt-0 lg:w-[980px] lg:overflow-visible xl:w-[1180px] xl:max-w-none 2xl:w-[1280px]">
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
</template>

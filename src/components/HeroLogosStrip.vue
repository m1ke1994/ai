<script setup>
const logos = ['/1.svg', '/2.svg', '/3.svg', '/4.svg', '/5.svg']
</script>

<template>
  <div class="mt-16 overflow-x-auto pb-1 sm:mt-20 lg:absolute lg:bottom-8 lg:left-0 lg:mt-0 lg:w-[1180px] lg:max-w-none lg:overflow-visible xl:w-[1280px]">
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

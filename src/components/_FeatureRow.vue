<template>
  <div class="bg-[#EDEFF4] rounded-2xl px-10 py-8 flex flex-col md:flex-row items-center justify-between gap-10">
    
    <!-- Left -->
    <div class="w-full md:w-1/3">
      <h4 class="text-2xl font-medium text-black">
        {{ title }}
      </h4>
    </div>

    <!-- Divider -->
    <div class="hidden md:block w-px bg-gray-300 h-20"></div>

    <!-- Middle -->
    <div class="w-full md:w-1/3 text-gray-600 text-lg">
      {{ description }}
    </div>

    <!-- Right slot -->
    <div class="w-full md:w-1/3 flex justify-end">
      <slot />
    </div>

  </div>
</template>

<script setup>
defineProps({
  title: String,
  description: String
})
</script>
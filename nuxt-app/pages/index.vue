<template>
  <main>
    <AppHeader />
    <div class="pt-[74px] lg:pt-[88px]">
      <HeroSection />
      <WhatSellerCan />
      <AiValueSection />
      <PricingSection />
      <IntegrationSteps />
      <ReviewsSection />
      <ContactFeedbackSection />
      <AppFooter />
    </div>
  </main>
</template>

<script setup>
import { onMounted } from 'vue'
import AppHeader from '~/components/AppHeader.vue'
import HeroSection from '~/components/HeroSection.vue'
import WhatSellerCan from '~/components/WhatSellerCan.vue'
import IntegrationSteps from '~/components/IntegrationSteps.vue'
import ReviewsSection from '~/components/ReviewsSection.vue'
import PricingSection from '~/components/PricingSection.vue'
import AiValueSection from '~/components/AiValueSection.vue'
import ContactFeedbackSection from '~/components/ContactFeedbackSection.vue'
import AppFooter from '~/components/AppFooter.vue'
import { useRevealOnScroll } from '~/composables/useRevealOnScroll'

onMounted(() => {
  useRevealOnScroll()
})
</script>

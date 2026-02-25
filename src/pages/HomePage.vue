<template>
  <div>
    <AppHeader />
    <div class="pt-[74px] lg:pt-[88px]">
      <HeroSection />
      <WhatSellerCan />
      <AutomationBusinessSection />
      <IntegrationSteps />
      <ReviewsSection />
      <ContactFeedbackSection />
      <AppFooter />
    </div>
  </div>
</template>

<script setup>
import AppHeader from '@/components/AppHeader.vue'
import AutomationBusinessSection from '@/components/AutomationBusinessSection.vue'
import HeroSection from '@/components/HeroSection.vue'
import WhatSellerCan from '@/components/WhatSellerCan.vue'
import IntegrationSteps from '@/components/IntegrationSteps.vue'
import ReviewsSection from '@/components/ReviewsSection.vue'
import ContactFeedbackSection from '@/components/ContactFeedbackSection.vue'
import AppFooter from '@/components/AppFooter.vue'
</script>

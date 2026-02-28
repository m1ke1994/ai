<template>
  <div>
    <AppHeader />
    <div class="pt-[74px] lg:pt-[88px]">
      <HeroSection />
      <WhatSellerCan />
       <AiValueSection />
      <IntegrationSteps />
      <ReviewsSection />
      <PricingSection />
    
        
      <ContactFeedbackSection />
    
      <AppFooter />
    </div>
  </div>
</template>

<script setup>
import AppHeader from '@/components/AppHeader.vue'

import Social_Media from '@/components/Social_Media.vue'
import HeroSection from '@/components/HeroSection.vue'
import WhatSellerCan from '@/components/WhatSellerCan.vue'
import IntegrationSteps from '@/components/IntegrationSteps.vue'
import ReviewsSection from '@/components/ReviewsSection.vue'
import PricingSection from '@/components/PricingSection.vue'
import AiValueSection from '@/components/AiValueSection.vue'
import ContactFeedbackSection from '@/components/ContactFeedbackSection.vue'
import AppFooter from '@/components/AppFooter.vue'
</script>

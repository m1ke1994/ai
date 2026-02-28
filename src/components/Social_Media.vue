<script setup>
import { siteData } from '@/assets/data'

const socialData = siteData.socialMedia
const { contactChannels } = socialData

const socialConfigByLabel = {
  Сайт: { href: '#', icon: '/icons/web.svg' },
  Telegram: { href: '#', icon: '/icons/telegram.svg' },
  Avito: { href: '#', icon: '/icons/avito.svg' },
  Instagram: { href: '#', icon: '/icons/instagram.svg' },
  Facebook: { href: '#', icon: '/icons/facebook.svg' },
  WhatsApp: { href: '#', icon: '/icons/whatsapp.svg' },
  YouTube: { href: '#', icon: '/icons/youtube.svg' },
  TikTok: { href: '#', icon: '/icons/tiktok.svg' },
  Mail: { href: '#', icon: '/icons/mail.svg' },
  ВКонтакте: { href: '#', icon: '/icons/vk.svg' },
  Max: { href: '#', icon: '/icons/Max.svg' },
}

const socialItems = contactChannels.map((label) => ({
  label,
  href: socialConfigByLabel[label]?.href || '#',
  icon: socialConfigByLabel[label]?.icon || siteData.assets.icons.check,
}))
</script>

<template>
  <!-- вњ… РљРѕРЅС‚Р°РєС‚С‹ / РћРјРЅРёРєР°РЅР°Р»СЊРЅРѕСЃС‚СЊ (С„РѕРЅ + С‚РµР»РµС„РѕРЅ) -->
  <div
    class="relative overflow-hidden rounded-[30px] border border-[#E1E5F2] bg-[#0b0f2a] p-5 pb-0 shadow-[0_22px_70px_rgba(18,26,52,0.18)] sm:rounded-[32px] sm:p-6 sm:pb-0 lg:p-7 lg:pb-0"
  >
    <!-- background image -->
    <img
      :src="siteData.assets.images.sectionBackground"
      alt=""
      aria-hidden="true"
      class="pointer-events-none absolute inset-0 h-full w-full object-cover opacity-[0.75]"
      draggable="false"
    />

    <!-- overlays -->
    <div
      aria-hidden="true"
      class="pointer-events-none absolute inset-0 bg-[linear-gradient(180deg,rgba(5,8,26,0.78)_0%,rgba(5,8,26,0.58)_45%,rgba(5,8,26,0.84)_100%)]"
    />
    <div
      aria-hidden="true"
      class="pointer-events-none absolute inset-0 opacity-[0.18]"
      style="
        background-image: repeating-linear-gradient(
          130deg,
          rgba(255, 255, 255, 0.20) 0px,
          rgba(255, 255, 255, 0.20) 1px,
          transparent 1px,
          transparent 16px
        );
      "
    />
    <div aria-hidden="true" class="pointer-events-none absolute -top-16 -right-24 h-64 w-64 rounded-full bg-[#6F63FF]/25 blur-3xl" />
    <div aria-hidden="true" class="pointer-events-none absolute -bottom-20 -left-24 h-64 w-64 rounded-full bg-[#7BB3FF]/20 blur-3xl" />

    <div class="relative grid gap-6 lg:grid-cols-[minmax(0,1.05fr)_minmax(0,0.95fr)] lg:items-center">
      <!-- LEFT: text + channels -->
      <div class="h-full rounded-[24px] p-4 shadow-[0_20px_50px_rgba(18,26,52,0.12)] sm:p-5 lg:p-6">
        <div
          class="inline-flex items-center gap-2 rounded-full border border-[#E3E8F6] bg-white px-3 py-1.5 text-[11px] font-medium tracking-[-0.01em] text-[#59607D]"
        >
          <span class="h-2 w-2 rounded-full bg-[#6F63FF] shadow-[0_0_14px_rgba(111,99,255,0.75)]" aria-hidden="true" />
          {{ socialData.pill }}
        </div>

        <h4 class="mt-4 text-[22px] font-semibold tracking-[-0.03em] text-[#fbfcfd] sm:text-[26px]">
          {{ socialData.title }}
        </h4>

        <p class="mt-2 max-w-[720px] text-[13px] leading-[1.55] text-[#fafbfc] sm:text-[14px]">
          {{ socialData.description }}
        </p>

        <div class="mt-5 grid grid-cols-2 gap-2.5 sm:grid-cols-3 lg:grid-cols-4">
          <a
            v-for="item in socialItems"
            :key="item.label"
            :href="item.href"
            :aria-label="item.label"
            class="group flex min-h-[44px] items-center justify-center gap-2 rounded-[14px] border border-[#E5E9F5] bg-white px-3 py-2 text-[12px] font-medium tracking-[-0.01em] text-black shadow-[0_10px_24px_rgba(0,0,0,0.08)] transition hover:-translate-y-0.5 hover:border-[#D3DAEF] hover:bg-[#FBFCFF]"
            @click.prevent="item.href === '#'"
          >
            <img
              :src="item.icon"
              :alt="item.label"
              class="h-4 w-4 shrink-0 object-contain opacity-90 transition group-hover:opacity-100"
            />
            <span class="truncate">{{ item.label }}</span>
          </a>
        </div>
      </div>

      <!-- RIGHT: phone (Р±РµР· РјР°С‚РѕРІРѕРіРѕ РєРѕРЅС‚РµР№РЅРµСЂР° + Р±РѕР»СЊС€Рµ СЂР°Р·РјРµСЂ + Р±РµР· РЅРёР¶РЅРµРіРѕ РѕС‚СЃС‚СѓРїР°) -->
      <div class="relative mx-auto w-full max-w-[620px] self-end">
        <div
          aria-hidden="true"
          class="pointer-events-none absolute -inset-10 rounded-[40px] bg-[radial-gradient(closest-side,rgba(111,99,255,0.22),transparent_70%)] blur-2xl"
        />
        <!-- СѓР±СЂР°Р»Рё: border/bg/padding/backdrop-blur -->
        <div class="relative flex items-end justify-center gap-3 sm:gap-4">
          <img
            :src="siteData.assets.images.socialPhone"
            :alt="socialData.phoneAlt"
            class="h-auto w-[46%] object-contain translate-y-[6px] sm:translate-y-[10px] lg:translate-y-[14px]"
            draggable="false"
          />
          <img
            :src="siteData.assets.images.socialPhoneSecondary || siteData.assets.images.socialPhone"
            :alt="`${socialData.phoneAlt} 2`"
            class="h-auto w-[46%] object-contain translate-y-[6px] sm:translate-y-[10px] lg:translate-y-[14px]"
            draggable="false"
            @error="($event) => ($event.target.src = siteData.assets.images.socialPhone)"
          />
        </div>
      </div>
    </div>
  </div>
</template>


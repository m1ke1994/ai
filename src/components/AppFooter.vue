<template>
  <footer class="bg-black">
    <div class="mx-auto max-w-[1840px] px-4 py-10 sm:py-12 lg:py-14">
      <div class="flex flex-col gap-8 lg:grid lg:grid-cols-[minmax(220px,520px)_1fr] lg:items-start lg:gap-x-10">
        <a href="/" class="inline-flex items-center gap-3 text-white" aria-label="Ai4Business">
          <img
            src="/logo.svg"
            alt="Ai4Business"
            class="h-11 w-auto rounded-full sm:h-[52px] lg:h-[58px]"
            draggable="false"
          />
          <span class="text-[20px] font-semibold leading-none tracking-[-0.02em] sm:text-[24px] lg:text-[26px]">
            Ai4Business
          </span>
        </a>

        <div class="flex flex-col gap-4 lg:gap-5">
          <nav class="flex flex-wrap items-center gap-x-6 gap-y-2 lg:gap-x-8" aria-label="Навигация в футере">
            <a
              v-for="item in navItems"
              :key="item.href"
              :href="item.href"
              class="text-[16px] font-semibold leading-none tracking-[-0.02em] text-white transition hover:text-[#8C81FF] sm:text-[18px] lg:text-[20px]"
            >
              {{ item.label }}
            </a>
          </nav>

          <div class="flex flex-wrap items-center gap-x-6 gap-y-2 lg:gap-x-8">
            <a
              href="mailto:support@mooonai.com"
              class="text-[15px] leading-none tracking-[-0.02em] text-[#8E91A9] transition hover:text-white sm:text-[17px] lg:text-[18px]"
            >
              support@mooonai.com
            </a>

            <a
              v-for="item in legalItems"
              :key="item.label"
              :href="item.href"
              class="text-[15px] leading-none tracking-[-0.02em] text-[#8E91A9] transition hover:text-white sm:text-[17px] lg:text-[18px]"
              @click.prevent="item.href === '#'"
            >
              {{ item.label }}
            </a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
const navItems = [
  { label: 'Преимущества', href: '#advantages' },
  { label: 'Этапы', href: '#steps' },
  { label: 'Отзывы', href: '#reviews' },
  { label: 'Контакты', href: '#contacts' },
  { label: 'Тарифы', href: '#pricing' },
]

const legalItems = [
  { label: 'Политика конфиденциальности', href: '#' },
  { label: 'Публичная оферта', href: '#' },
  { label: 'Пользовательское соглашение', href: '#' },
]
</script>

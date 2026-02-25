<script setup>
const navItems = [
  { label: 'Преимущества', href: '#advantages' },
  { label: 'Этапы', href: '#steps' },
  { label: 'Отзывы', href: '#reviews' },
  { label: 'Контакты', href: '#contacts' },
  { label: 'Тарифы', href: '#pricing' },
]
</script>

<template>
  <header
    class="fixed left-0 top-0 z-[100] w-full border-b border-white/10 bg-[#02030A] shadow-[0_8px_28px_rgba(0,0,0,0.24)]"
  >
    <div class="mx-auto max-w-[1720px] px-4 sm:px-6 lg:px-10">
      <div class="relative flex h-[74px] items-center justify-between lg:h-[88px]">
        <a href="/" class="flex items-center gap-3 text-white">
          <span class="block w-[34px] overflow-hidden sm:w-[36px]" aria-hidden="true">
            <img src="/logo.svg" alt="" class="h-7 w-auto max-w-none sm:h-8" />
          </span>
          <span class="text-[22px] font-semibold leading-none tracking-[-0.02em] sm:text-[24px]">
            MoonAI
          </span>
        </a>

        <nav
          class="absolute left-1/2 top-1/2 hidden -translate-x-1/2 -translate-y-1/2 items-center gap-8 lg:flex xl:gap-14"
          aria-label="Основная навигация"
        >
          <a
            v-for="item in navItems"
            :key="item.href"
            :href="item.href"
            class="text-[15px] font-medium text-[#A8ABC3] transition-colors duration-200 hover:text-white"
          >
            {{ item.label }}
          </a>
        </nav>

        <div class="hidden items-center gap-5 md:flex lg:gap-8">
          <a
            href="/login"
            class="text-[15px] font-medium text-[#B4B7CD] transition-colors duration-200 hover:text-white"
          >
            Логин
          </a>
          <a
            href="/register"
            class="inline-flex h-10 items-center rounded-xl border border-white/15 bg-white/[0.02] px-4 text-[15px] font-medium text-[#ECEEFA] transition duration-200 hover:border-white/25 hover:bg-white/5"
          >
            Регистрация
          </a>
        </div>
      </div>
    </div>
  </header>
</template>

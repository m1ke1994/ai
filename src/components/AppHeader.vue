<template>
  <header class="w-full border-b border-white/10 bg-[#0B0F1A]">
    <div class="max-w-7xl mx-auto px-6">
      <div class="flex items-center justify-between h-16">
        
        <!-- Лого -->
        <div class="flex items-center space-x-3">
          <div class="flex space-x-1">
            <span class="w-2 h-2 bg-purple-500 rounded-full"></span>
            <span class="w-2 h-2 bg-purple-500 rounded-full"></span>
            <span class="w-2 h-2 bg-purple-500 rounded-full"></span>
          </div>
          <span class="text-white text-xl font-semibold">MoonAI</span>
        </div>

        <!-- Навигация -->
        <nav class="hidden md:flex items-center space-x-10 text-gray-300 text-sm">
          <a href="#advantages" class="hover:text-white transition">Преимущества</a>
          <a href="#steps" class="hover:text-white transition">Этапы</a>
          <a href="#reviews" class="hover:text-white transition">Отзывы</a>
          <a href="#contacts" class="hover:text-white transition">Контакты</a>
          <a href="#pricing" class="hover:text-white transition">Тарифы</a>
        </nav>

        <!-- Авторизация -->
        <div class="hidden md:flex items-center space-x-6 text-sm">
          <a href="/login" class="text-gray-300 hover:text-white transition">
            Логин
          </a>
          <a
            href="/register"
            class="text-white border border-white/20 px-4 py-2 rounded-lg hover:bg-white hover:text-black transition"
          >
            Регистрация
          </a>
        </div>

      </div>
    </div>
  </header>
</template>

<script setup>
// логика не требуется
</script>
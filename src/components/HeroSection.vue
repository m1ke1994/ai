<template>
  <section class="relative overflow-hidden bg-gradient-to-br from-[#070B1F] via-[#0E1333] to-[#1B1F4A]">
    
    <!-- Декоративные круги -->
    <div class="absolute -left-40 top-20 w-[600px] h-[600px] bg-purple-600/10 rounded-full blur-3xl"></div>
    <div class="absolute right-0 bottom-0 w-[500px] h-[500px] bg-indigo-600/10 rounded-full blur-3xl"></div>

    <div class="relative max-w-7xl mx-auto px-6 py-24 flex items-center justify-between gap-10">
      
      <!-- ЛЕВАЯ ЧАСТЬ -->
      <div class="max-w-2xl">
        <h1 class="text-5xl md:text-6xl font-semibold leading-tight text-white">
          Запустите ИИ-продажника <br />
          для отдела продаж <br />
          <span class="text-purple-400">
            за 1 день — бесплатно
          </span>
        </h1>

        <p class="mt-6 text-lg text-gray-400 max-w-xl">
          Он будет квалифицировать заявки 24/7, переводить тёплых лидов менеджерам 
          и экономить до 40% времени отдела продаж
        </p>

        <button
          class="mt-10 px-8 py-4 rounded-xl text-white text-lg font-medium
                 bg-gradient-to-r from-purple-600 to-indigo-500
                 hover:opacity-90 transition shadow-lg shadow-purple-500/20"
        >
          Подключить ИИ-продажника
        </button>

        <!-- Логотипы -->
        <div class="mt-16 flex flex-wrap items-center gap-10 opacity-60">
          <div class="w-28 h-8 bg-white/10 rounded"></div>
          <div class="w-24 h-8 bg-white/10 rounded"></div>
          <div class="w-32 h-8 bg-white/10 rounded"></div>
          <div class="w-28 h-8 bg-white/10 rounded"></div>
          <div class="w-24 h-8 bg-white/10 rounded"></div>
          <div class="w-20 h-8 bg-white/10 rounded"></div>
        </div>
      </div>

      <!-- ПРАВАЯ ЧАСТЬ -->
      <div class="relative hidden lg:block">

        <!-- Телефон-заглушка -->
        <div class="relative w-[360px] h-[720px] rounded-[40px] 
                    bg-gradient-to-br from-gray-900 to-black
                    border border-white/10 shadow-2xl">
          
          <div class="absolute inset-4 rounded-[30px] bg-black flex items-center justify-center text-gray-600">
            IMAGE
          </div>
        </div>

        <!-- Floating badges -->
        <div class="absolute top-32 -left-24 px-4 py-2 bg-white/10 backdrop-blur-md 
                    text-white rounded-full text-sm border border-white/10">
          ✨ Точно
        </div>

        <div class="absolute top-52 -left-20 px-4 py-2 bg-white/10 backdrop-blur-md 
                    text-white rounded-full text-sm border border-white/10">
          ✨ Быстро
        </div>

        <div class="absolute bottom-40 -left-16 px-6 py-3 
                    bg-gradient-to-r from-purple-600 to-indigo-500
                    text-white rounded-full text-sm shadow-lg">
          ✨ Автономно
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
// логика не требуется
</script>
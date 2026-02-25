<template>
  <section class="bg-[#F3F4F7] py-24">

    <!-- ====== TOP STATS ====== -->
    <div class="max-w-6xl mx-auto px-6">
      <div class="bg-white rounded-3xl shadow-sm flex flex-col md:flex-row divide-y md:divide-y-0 md:divide-x divide-gray-200 overflow-hidden">

        <!-- 0 тг -->
        <div class="flex-1 py-14 text-center">
          <div class="text-5xl font-semibold text-black">0 тг</div>
          <p class="mt-4 text-gray-500 text-lg">
            за установку ИИ
          </p>
        </div>

        <!-- 100% -->
        <div class="flex-1 py-14 text-center">
          <div class="text-5xl font-semibold text-black">100%</div>
          <p class="mt-4 text-gray-500 text-lg max-w-sm mx-auto">
            верификация от meta, google,<br />
            amocrm, bitrix и другие
          </p>
        </div>

        <!-- 24/7 -->
        <div class="flex-1 py-14 text-center">
          <div class="text-5xl font-semibold text-black">24/7</div>
          <p class="mt-4 text-gray-500 text-lg">
            поддержка от проектных менеджеров
          </p>
        </div>

      </div>
    </div>


    <!-- ====== TITLE ====== -->
    <div class="text-center mt-24">
      <h2 class="text-4xl font-semibold text-black">
        Что умеет
      </h2>
      <h3 class="text-4xl font-semibold text-gray-400 mt-2">
        AI продавец
      </h3>
    </div>


    <!-- ====== FEATURES ====== -->
    <div class="max-w-6xl mx-auto px-6 mt-20 space-y-6">

      <!-- Мультиязычность -->
      <FeatureRow
        title="Мультиязычность"
        description="Идеально говорит на русском, английском и даже шала-казахском"
      >
        <div class="flex items-center gap-4">
          <div class="w-12 h-12 bg-gray-200 rounded-full"></div>
          <div class="w-12 h-12 bg-gray-200 rounded-full"></div>
          <div class="w-12 h-12 bg-gray-200 rounded-full"></div>
          <span class="text-purple-500 font-medium ml-2">150+ языков</span>
        </div>
      </FeatureRow>

      <!-- Интеграция с МойСклад -->
      <FeatureRow
        title="Интеграция с МойСклад"
        description="Знает какой товар есть в наличии"
      >
        <div class="bg-green-500 rounded-xl px-6 py-4 text-white flex items-center gap-4 shadow-md">
          <div class="w-10 h-10 bg-white/20 rounded"></div>
          <div>
            <div class="font-medium">Есть в наличии</div>
            <div class="h-2 bg-white/30 rounded mt-2 w-40"></div>
          </div>
        </div>
      </FeatureRow>

      <!-- Запись клиентов -->
      <FeatureRow
        title="Запись клиентов"
        description="Назначает клиентам встречи и записи"
      >
        <div class="flex items-center gap-4">
          <div class="w-12 h-12 bg-black rounded-full"></div>
          <div class="w-12 h-12 bg-gray-200 rounded-full"></div>
          <div class="w-12 h-12 bg-purple-500 rounded-full"></div>
        </div>
      </FeatureRow>

      <!-- Работа с файлами -->
      <FeatureRow
        title="Работа с файлами"
        description="Читает любые файлы"
      >
        <div class="flex flex-wrap gap-3">
          <span class="px-4 py-2 bg-gray-200 rounded-lg text-gray-700">Чеки</span>
          <span class="px-4 py-2 bg-gray-200 rounded-lg text-gray-700">КП</span>
          <span class="px-4 py-2 bg-gray-200 rounded-lg text-gray-700">Договоры</span>
          <span class="px-4 py-2 bg-gray-200 rounded-lg text-gray-700">Изображения</span>
          <span class="px-4 py-2 bg-gray-200 rounded-lg text-gray-700">Аудио</span>
        </div>
      </FeatureRow>

      <!-- Upsell -->
      <FeatureRow
        title="Upsell и дожим"
        description="Дожимает клиентов, используя собранную информацию"
      >
        <div class="bg-white rounded-xl p-4 shadow-md w-72 text-sm text-gray-700">
          Можем записать вас на пробный урок с нашим преподавателем,
          где поможем подобрать курс под вас.
        </div>
      </FeatureRow>

      <!-- Интеграция CRM -->
      <FeatureRow
        title="Интеграция CRM"
        description="Работает с популярными CRM системами"
      >
        <div class="flex items-center gap-4">
          <div class="w-12 h-12 bg-gray-200 rounded-lg"></div>
          <div class="w-12 h-12 bg-gray-200 rounded-lg"></div>
          <div class="w-12 h-12 bg-gray-200 rounded-lg"></div>
        </div>
      </FeatureRow>

    </div>
  </section>
</template>

<script setup>
import FeatureRow from './_FeatureRow.vue'
</script>
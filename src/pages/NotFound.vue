<template>
  <section class="rounded-2xl border border-rose-400/20 bg-rose-400/10 p-6">
    <p class="text-sm font-medium uppercase tracking-[0.2em] text-rose-300">404</p>
    <h1 class="mt-2 text-2xl font-bold text-white">Страница не найдена</h1>
    <p class="mt-2 text-slate-300">Проверьте адрес или вернитесь на главную страницу.</p>
    <RouterLink
      to="/"
      class="mt-4 inline-flex items-center rounded-xl bg-white px-4 py-2 font-semibold text-slate-900 transition hover:bg-slate-100"
    >
      На главную
    </RouterLink>
  </section>
</template>

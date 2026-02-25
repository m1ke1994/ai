<template>
  <div class="min-h-screen">
    <header class="sticky top-0 z-10 border-b border-white/10 bg-slate-950/80 backdrop-blur">
      <div class="mx-auto flex max-w-5xl items-center justify-between px-4 py-4">
        <RouterLink to="/" class="text-lg font-semibold tracking-tight text-white">
          Vue 3 Starter
        </RouterLink>
        <nav class="flex items-center gap-2 text-sm font-medium">
          <RouterLink
            to="/"
            class="rounded-full px-3 py-1.5 text-slate-300 transition hover:bg-white/5 hover:text-white"
          >
            Home
          </RouterLink>
          <RouterLink
            to="/about"
            class="rounded-full px-3 py-1.5 text-slate-300 transition hover:bg-white/5 hover:text-white"
          >
            About
          </RouterLink>
        </nav>
      </div>
    </header>

    <main class="mx-auto w-full max-w-5xl px-4 py-8">
      <slot />
    </main>
  </div>
</template>

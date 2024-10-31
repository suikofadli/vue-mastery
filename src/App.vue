<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header class="p-5">
    <nav class="flex gap-5 justify-center">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>

  <div class="max-w-2xl p-5 mx-auto">
    <RouterView />
  </div>
</template>

<style scoped></style>

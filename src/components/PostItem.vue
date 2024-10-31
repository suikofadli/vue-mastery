<script setup>
defineProps({
  post: {
    type: Object,
    required: true
  }
})

</script>

<template>
  <RouterLink :to="{ name: 'posts.show', params: { id: post.id } }">
    <div class="border p-4 rounded transition hover:scale-105">
      <h1 class="font-bold mb-2 text-lg">{{ post.title }}</h1>
      <p>
        {{ post.body }}
      </p>
    </div>
  </RouterLink>
</template>

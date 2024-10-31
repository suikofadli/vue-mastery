<script setup>
import PostItem from '@/components/PostItem.vue';
import PostService from '@/services/PostService';
import { onMounted, ref } from 'vue';

const posts = ref([])

onMounted(() => {
  PostService.getPosts()
    .then(response => {
      posts.value = response.data
    })
    .catch(err => {
      console.log(err)
    })
})

</script>

<template>
  <div class="grid gap-5">
    <PostItem v-for="post in posts" :key="post.id" :post="post" />
  </div>
</template>

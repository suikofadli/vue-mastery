<script setup>
import PostService from '@/services/PostService';
import { onMounted, ref } from 'vue';

const props = defineProps({
  id: String
})

const post = ref(null)

onMounted(() => {
  PostService.getPost(props.id)
    .then((response) => {
      post.value = response.data
    })
    .catch(err => {
      console.log(err)
    })
})

</script>

<template>
  <div v-if="!post">
    Loading...
  </div>

  <div v-if="post">
    <h1 class="text-xl font-bold">
      {{ post.title }}
    </h1>

    <p>
      {{ post.body }}
    </p>
  </div>
</template>

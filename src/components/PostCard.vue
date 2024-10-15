<template>
  <div class="post-card">
    <h3>Titulo</h3>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Labore commodi molestiae quas deleniti vero! Repellendus doloremque delectus distinctio sint fuga enim, nesciunt laboriosam unde autem officiis repudiandae. Sapiente, fugit maxime!</p>

    <PostButton />
  </div>
</template>

<script lang="ts" setup>
  import PostButton from './PostButton.vue';
</script>

<style scoped>
  .post-card{
    border-radius: 15px;
    padding: 10px;
    margin: 5px;
    border: 1px solid #ccc;
  }
</style>
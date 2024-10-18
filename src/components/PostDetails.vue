<template>
  <div class="post">
    <h3>{{ props.title }}</h3>
    <p>{{ props.content }}</p>
    <button @click="sendAlert">Necesito mas post</button>
  </div>
</template>

<script lang="ts" setup>
import { defineProps, defineEmits, Ref, ref } from 'vue';
const props = defineProps({
  title: String,
  content: String
})

const emit = defineEmits(['alertMsg'])

const sendAlert = () => {
  emit("alertMsg", "Necesito mas post por favor")
}

let message: Ref<string> = ref("")

</script>

<style scoped>
.post {
  width: 300px;
  height: 200px;
  background-color: aqua;
  border-radius: 10px;
  margin: 10px;
  padding: 10px;
}
</style>
<template>
  <div class="post">
    <h3>{{ props.title }}</h3>
    <p>{{ props.content }}</p>
    <button @click="sendAlert">Necesito mas post</button>
  </div>
</template>

<script lang="ts">
  import { defineComponent, Ref, ref } from 'vue';

  export default defineComponent({
    name: 'PostDetails',
    props: {
      title: {
        type: String,
        required: true
      },
      content: {
        type: String,
        required: false,
        default: "Este post no tiene contenido"
      }
    },
    emits: ["alertMsg"],
    setup(props, {emit}) {
      const sendAlert = () => {
        emit("alertMsg", "Necesito mas post por favor")
      }
      return { props, sendAlert }
    }
  })
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
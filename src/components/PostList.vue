<template>
  <div class="container">
    <PostDetails v-for="elm in info" :key="elm.title" :title="elm.title" 
    :content="elm.content" @alertMsg="showAlert"/>
  </div>
</template>

<script lang="ts" setup>
  import PostDetails from './PostDetails.vue';

  interface PostInfo{
    title: string,
    content: string
  }

  let info: Array<PostInfo> = [
    {
      title: 'Energias Renovables',
      content: "Bienvenidos al post de Energias Renovables"
    },
    {
      title: "Conciencia a la medida",
      content: "Conciencia ¿Que es?"
    },
    {
      title: "Ley de Atraccion",
      content: "Puedes conseguir lo que necesitas si lo llamas"
    },
    {
      title: "Nuevas Vidas",
      content: "Una nueva vida, ¿Es posible?"
    },
    {
      title: "Aquello quedo atras",
      content: "Dejas atras todo lo que lastima"
    }
  ]

  function showAlert(msg: string){
    alert(msg)
  }
</script>

<style scoped>
.container{
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: space-around;
}
</style>
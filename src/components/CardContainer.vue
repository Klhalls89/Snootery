
<template>
  <div id="CardContainer">
    <div v-bind:key="image.id" v-for="image in images">
       <GalleryCard v-bind:image="image" />
    </div>
  </div>
</template>

<script>
import GalleryCard from './GalleryCard.vue'

export default {
  name: 'CardContainer',
  props: ["images"],
  components: {
    GalleryCard
  }
}
</script>

<style scoped>
#CardContainer {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(20rem, 1fr));
  grid-gap: 1rem;
  max-width: 80rem;
  margin: 5rem auto;
  padding: 0 5rem;
}


h3 {
  font-family: 'Fondamento', cursive;
  color: #A51C31;
  text-align:  center;
  font-size: 1.5rem;
}
</style>

<template>
  <div id="CardContainer">
    <h3>card container</h3>
    <GalleryCard />
  </div>
</template>

<script>
import GalleryCard from './GalleryCard.vue'

export default {
  name: 'CardContainer',
  components: {
    GalleryCard
  }
}
</script>

<style scoped>

#CardContainer {
  display: grid;
}


h3 {
  font-family: 'Fondamento', cursive;
  color: #A51C31;
  text-align:  center;
  font-size: 1.5rem;
}

</style>
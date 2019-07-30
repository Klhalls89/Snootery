<template>
  <div id="GalleryCard">
    <img v-bind:src="image.baseimageurl"/>
    <p>{{image.date}}</p>
  </div>
</template>

<script>
export default {
  name: 'GalleryCard',
  props: ["image"],
  components: {
  }
}
</script>

<style scoped>

#GalleryCard {
  display: inline-block;
  height: 500px;
  width: 500px;
}

img {
  height: 340px;
  width: 340px;
}

</style>
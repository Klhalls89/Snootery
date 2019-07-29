<template>
  <div id="app">
    <h1>Snootery</h1>
    <CardContainer />
  </div>
</template>

<script>
import CardContainer from './components/CardContainer.vue'

export default {
  name: 'app',
  components: {
   CardContainer
  },
  data() {
    return {
      gallery: []
    }
  },
}
</script>

<style>
* {
  box-sizing: border-box;
  font-family: 'Open Sans', sans-serif;
}

body {
  text-align: center;
}

h1 {
  font-family: 'Fondamento', cursive;
  color: #A51C31;
  text-align:  center;
  font-size: 3rem;
}

</style>

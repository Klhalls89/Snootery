<template>
  <div id="app">
    <h1><i class="fas fa-wine-glass-alt"></i>Snootery</h1>
    <CardContainer v-if="this.$root.$data.images.length" v-bind:images="this.$root.$data.images" />
  </div>
</template>

<script>
import CardContainer from './components/CardContainer.vue'
import  key  from '../key.js'
const url = "https://api.harvardartmuseums.org/image?apikey=" + key + "&size=50"

export default {
  name: 'app',
  components: {
   CardContainer
  },
  methods : {
    fetchData() {
      fetch(url)
      .then(result =>  result.json())
      .then(data => this.setData(data))
      .catch(error => error)
    },
    setData(art) {
      this.$root.$data.images = art.records
    }
  },
   beforeMount(){
    this.fetchData()
 },

  data() {
    return {
      images: []
    }
  },
}
</script>

<style>
* {
  box-sizing: border-box;
  font-family: 'Open Sans', sans-serif;
  margin: 0;
}

body {
  text-align: center;
}

h1 {
  font-family: 'Fondamento', cursive;
  color: #A51C31;
  text-align:  center;
  font-size: 3rem;
  background-color: #f4f1e6;
}

#app {
  background-image: url(./bg.png);
  background-repeat: no-repeat;
  background-size: cover;
}
.fas {
  margin: 5px;
}
</style>

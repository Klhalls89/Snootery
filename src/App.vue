<template>
  <div id="app">
    <h1>Snootery</h1>
    <CardContainer />
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
      .catch(error => console.log(error))
    },
    setData(art) {
      this.$root.$data.gallery = art.records
      console.log(this.$root.$data.gallery)
    }
  },
   beforeMount(){
    this.fetchData()
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

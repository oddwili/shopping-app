<template>
  <div id="app">
    <HelloWorld msg="Shopping App"/>
    <Showcase v-bind:photos="photos"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Showcase from './components/Showcase.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Showcase
  },
  data() {
    return {
      photos: null
    }
  },
  mounted () {
    fetch('https://jsonplaceholder.typicode.com/photos/?limit=10')
      .then(response => response.json())
      .then(json => (this.photos = json));
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

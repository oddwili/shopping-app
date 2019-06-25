<template lang="html">
  <div class="showcase">
      <h2>showcase</h2>
      <div class="showcase-tile"
        v-for="photo in photos"
        v-bind="photo">
        <img :src="photo.thumnailUrl" alt="photo thumbnail">
        <p>{{photo.title}}</p>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Showcase',
  props: ["photos"]
}
</script>

<style lang="css" scoped>
</style>

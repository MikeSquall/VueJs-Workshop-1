<template>
  <div class="col card bg-light col-6">
    <div v-if="!beers.length">Loading beers !</div>
    <div id="beer-list">
      <div
        class="list-group"
        v-for="beer in beers"
        :key="beer.id">
        <button
          class="list-group-item"
          style="white-space: normal;"
        >
          <h5 class="text-left">{{ beer.name }}</h5>
          <h6 class="text-left text-muted">{{ beer.tagline }}</h6>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import BeerDetails from './BeerDetails.vue'

export default {
  name: 'BeerList',
  props: ['beers'],
  components: {
    BeerDetails
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.beers-list{
  min-height: 500px;
}
</style>

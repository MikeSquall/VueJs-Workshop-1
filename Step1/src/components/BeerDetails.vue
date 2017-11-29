<template>
  <div class="col-6 card pt-4">
    <div class="card-body">
      <div class="row">
        <div class="col-3 text-center">
          <img :src="beer.image_url" :alt="beer.name" class="beer-image image-responsive"/>
        </div>
        <div class="col">
          <h3 class="beer-name">{{ beer.name }}</h3>
          <h6 class="tagline">{{ beer.tagline }}</h6>
          <p><span class="p-label">Deg:</span> {{ beer.abv }}</p>
          <p><span class="p-label">Food pairing:</span> {{ beer.food_pairing.join(', ') }}</p>
        </div>
      </div>
      <p><span class="p-label">Description:</span> {{ beer.description }}</p>
      <p><span class="p-label">Brewer Tips:</span> {{ beer.brewers_tips }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BeerDetails',
  props: ['beer']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card{
  display: inline-flex;
}
.beers-list{
  min-height: 500px;
}
.beer-image{
  height: 150px;
}
.tagline{
  color: #888;
}
.p-label{
  font-weight: bold;
}
</style>

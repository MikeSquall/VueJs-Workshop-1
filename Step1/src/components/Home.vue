<template>
  <div class="container">
    <div class="row card-group">
      <!-- BEER LIST -->
      <BeerList :beers="beer_list" @click="onClickBeerList"></BeerList>
      <BeerDetails :beer="beer_list[7]" v-if="beer_list.length"></BeerDetails>
    </div>
  </div>
</template>

<script>
import BeerList from './BeerList'
import BeerDetails from './BeerDetails.vue'
import axios from 'axios'

export default {
  name: 'home',
  data () {
    return {
      beer_list: [],
      test_beer: {
        name: 'toto',
        image_url: 'http://bit.ly/2AmOYzc',
        tagline: 'wazaaaaaaa !!',
        abv: '42',
        food_pairing: ['any food'],
        description: 'very good beer',
        brewers_tips: 'drink it !'
      },
      selected_beer: null
    }
  },
  mounted () {
    axios.get('https://api.punkapi.com/v2/beers?per_page=10')
    .then(response => {
      this.beer_list = response.data
    })
  },
  components: {
    BeerList,
    BeerDetails
  },
  methods: {
    onClickBeerList (value) {
      console.log(value)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.beers-list{
  min-height: 500px;
}
</style>

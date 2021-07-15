<template>
  <div v-if="records.length === 10" id="app">
    <Nav @filter="genreOption" :genres="genres"/>
    <Main :records="filteredRecords" />
  </div>
  <div v-else class="loading-screen">
    <Loader />
  </div>
</template>

<script>
import axios from 'axios'
import Nav from './components/Nav.vue'
import Main from './components/Main.vue'
import Loader from './components/Loader.vue'

export default {
  name: 'App',
  components: {
    Nav,
    Main,
    Loader
  },
  data () {
    return {
      records: [],
      genres: [],
      selectedGenre: 'All',
    }
  },

  created() {
    setTimeout(() => { // Gives time to show the loading screen!
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((reply) => {
        this.records = reply.data.response;

        reply.data.response.forEach(element => {

          if(!this.genres.includes(element.genre)) {
            this.genres.push(element.genre)
          }
        });

      }) 
    }, 2000)
  },

  methods: {

    genreOption(selectedOption) {
      this.selectedGenre = selectedOption;
    },

  },

  computed: {
    filteredRecords() {

      if (this.selectedGenre === 'All') {
        return this.records;
      }

      return this.records.filter((element) => {

        if (element.genre === this.selectedGenre) {
          return true;
        } else {
          return false;
        }
      })

    },
  },

}
</script>

<style lang="scss">

@import './style/app.scss';

</style>

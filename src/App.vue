<template>
  <div v-if="records.length === 10" id="app">
    <Nav />
    <Main :records="records" />
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
    }
  },
  created() {
    setTimeout(() => { // Gives time to show the loading screen!
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((reply) => {
        this.records = reply.data.response;
      }) 
    }, 2000)
  }
}
</script>

<style lang="scss">

@import './style/app.scss';

</style>

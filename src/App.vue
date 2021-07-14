<template>
  <div id="app">
    <Nav />
    <Main :records="records" />
  </div>
</template>

<script>
import axios from 'axios'
import Nav from './components/Nav.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Nav,
    Main
  },
  data () {
    return {
      records: [],
    }
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((reply) => {
      this.records = reply.data.response;
    }) 
  }
}
</script>

<style lang="scss">

@import './style/app.scss';

</style>

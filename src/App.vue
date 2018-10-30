<template>
  <div id="app">
    <Header/>
    <div class="container">
      <div class="row">
        <div class="col-md-4">
          <DecaFilter></DecaFilter>
        </div>
      </div>
      
      <div class="row">
        <DecaMap name="DecaMap"></DecaMap>
      </div>  

      <DecaThumb></DecaThumb>
    </div>
  </div>
</template>

<script>
import Header from './components/Header'
import DecaFilter from './components/DecaFilter'
import DecaMap from './components/DecaMap'
import DecaThumb from './components/DecaThumb'
import axios from 'axios'

export default {
  name: 'app',
  components: {
      DecaFilter,
      DecaMap,
      DecaThumb,
      Header
  },
  data () {
    return {
      // sports: null,
      // places: null,
     info: null
    }
  },
  mounted () {
  }
}

</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  padding: 0;
}
</style>
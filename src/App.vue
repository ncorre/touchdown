<template>
  <div id="app">
    <DecaFilter></DecaFilter>
    <DecaMap></DecaMap>
    <div>
        <DecaThumb></DecaThumb>
    </div>
    
  </div>
</template>

<script>
import DecaFilter from './components/DecaFilter'
import DecaMap from './components/DecaMap'
import DecaThumb from './components/DecaThumb'

export default {
  name: 'app',
  components: {
      DecaFilter,
      DecaMap,
      DecaThumb
  }
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
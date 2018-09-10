<template>
    <b-form-select :options="options" class="col-md-4 col-sm-12">
      <option v-for="sport in sports.data" :key="sport.id" :value="sport.id" >{{sport.name}}</option>
    </b-form-select>
</template>

<script>
import axios from 'axios'

  export default {
    data: function () {
    return {
      options: '',
      sports: null
    }
    },
    mounted () {
    axios
      .get("https://sportplaces.api.decathlon.com/api/v1/sports")
      .then(response => (this.sports = response))
      .catch(error => console.log(error))
   }
  }
</script>

<style>
</style>
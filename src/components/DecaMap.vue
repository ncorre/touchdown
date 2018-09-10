<template>
    <div class="google-map" :id="mapName"></div>
</template>

<script>
export default {
  name: 'google-map',
  props: ['name'],
  data: function () {
    return {
      mapName: this.name + "-map",
      markerCoordinates: [{
      latitude: 45.5086644,
      longitude: -73.6132455
    }, {
      latitude: 45.5152453,
      longitude: -73.5830235
    }, {
      latitude: 45.5329897,
      longitude: -73.6271729
    },
     {
      latitude: 45.5353481,
      longitude: -73.6282682
    },
     {
      latitude: 45.5263638,
      longitude: -73.5693448
    },
     {
      latitude: 45.5535893,
      longitude: -73.5899291
    },
    {
      latitude: 45.553186,
      longitude: -73.638784
    },
    {
      latitude: 45.5054418,
      longitude: -73.5050324
    }]
    }
  },
  mounted: function () {
    const element = document.getElementById(this.mapName)
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(45.5034853,-73.6094457)
    }
    const map = new google.maps.Map(element, options);
    this.markerCoordinates.forEach((coord) => {
    const position = new google.maps.LatLng(coord.latitude, coord.longitude);
    const marker = new google.maps.Marker({ 
    position,
    map
  });
});
  }
};
</script>

<style scoped>
.google-map {
  width: calc(100vw);
  height: 500px;
  margin: 0 auto;
  border: 1px solid grey;
  margin-top: 25px;
  margin-bottom: 25px;
}
</style>
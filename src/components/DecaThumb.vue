<template>
<div>
  <div class="row row-marged" v-for="thumb in thumbnails.data" :key="thumb.sport_id">
    <div v-for="(info, index) in thumb.features" v-if="index < 4" :key="index">
      <b-card
              img-src="https://picsum.photos/600/300/?image=10"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem;"
              class="mb-2">
        <h3>{{info.properties.name}}</h3>
        <div class="informations-thumb">
          <p class="card-text card-adress">Adress : {{info.properties.address_components.address}}</p>
          <p class="card-text" v-if="info.properties.contact_details.phone">Tel : {{info.properties.contact_details.phone}}</p>
          <p class="card-text" v-if="info.properties.address_components.email">Email : {{info.properties.address_components.email}}</p>
          <ul class="activities">
            activités disponibles:
            <li v-for="(activities, index) in info.properties.activities" v-if="index < 3" :key="index">
              {{activities.sport_id}}
            </li>
        </ul>

        </div>
        
      </b-card>
    </div >
  </div>
</div>


</template>

<script>
import axios from 'axios'

export default {
  data: function (index) {
    return {
      selectedSport: null,
      counter: 0,
      thumbnails: null
    }
  },
  mounted () {
    axios
      .get("https://sportplaces.api.decathlon.com/api/v1/places?origin=-73.6091669%2C45.5012326&page=1&radius=99")
      .then(response => (this.thumbnails = response))
      .catch(error => console.log(error))
   },
}
</script>


<style>
.deca-location:before {
  content: '';
  background: url('../assets/img/placeholder-filled-point.png');
  display: block;
  position: absolute;
  left: 100px;
  bottom: 20px;
  width: 24px;
  height: 24px;
}
.row-marged {
  margin: 0 !important;
  justify-content: space-evenly;
}
h3 {
  font-size: 1.50rem;
  display: block;
  height: 119px;
  width: 238px;
  position: absolute;
  top: 35px;
  left: 5px;
  text-align: center;
  color: white;
  font-weight: bold;
  transform: rotate(-10deg);
}
.informations-thumb {
  display: block;
}
.card {
  max-width: 15rem !important;
  border-radius: 1em;
  box-shadow: 0 4px 12px 0 rgba(0,0,0,0.3);
}
.card-img-top {
  border-top-left-radius: 1rem;
  border-top-right-radius: 1rem;
}
.card-text {
  text-align: left;
  margin-bottom: 5px;
}
.card-adress {
  height: 48px;
}
.italic-txt {
  font-style: italic;
}
.activities {
  list-style: none;
  text-align: left;
  padding: 0;
  margin-bottom: 0;
}
.activities li {
  list-style: none;
}
.activities li:before {
  content:'> ';
  display: inline-block;
}
</style>

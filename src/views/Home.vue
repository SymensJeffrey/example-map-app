<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div id='map' style='width: 400px; height: 300px;'></div>
  </div>

</template>


<style>

</style>


<script>
import mapboxgl from 'mapbox-gl'; // or "const mapboxgl = require('mapbox-gl');"

export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!"
    };
  },
  mounted: function() {
    this.doMapBox();
  },
  methods: {
    doMapBox: function() {
      mapboxgl.accessToken = process.env.VUE_APP_MAP_API_KEY;
      const map = new mapboxgl.Map({
      container: 'map', // container ID
      style: 'mapbox://styles/mapbox/streets-v11', // style URL
      center: [-74.5, 40], // starting position [lng, lat]
      zoom: 9 // starting zoom
      });
    }
  }
};
</script>
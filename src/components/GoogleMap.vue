<template>
  <gmap-map
    :center="center"
    :zoom="18"
    style="width:100%; height: 300px"
  >
    <gmap-marker
      :key="index"
      v-for="(m, index) in markers"
      :position="m.position"
      :clickable="true"
      :draggable="true"
      @click="center=m.position"
    ></gmap-marker>
  </gmap-map>
</template>
 
<script>
  // New in 0.4.0
  import * as VueGoogleMaps from 'vue2-google-maps'
  import Vue from 'vue'
  Vue.use(VueGoogleMaps, {
    load: {
      key: 'AIzaSyBgRkQ8DHOokMuR_WKzxtS3aZkKPwqOsG4',
      v: '3.30',
      libraries: 'places' // If you need to use place input
    }
  })

  export default {
    data () {
      return {
        center: {lat: 47.748073, lng: -122.358366},
        markers: [{
          position: {lat: 47.74807, lng: -122.358366}
        }, {
          position: {lat: 47.748073, lng: -122.3583}
        }]
      }
    }
  }
</script> 
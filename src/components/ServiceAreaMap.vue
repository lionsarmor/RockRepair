<template>
  <LMap
    :zoom="zoom"
    :center="center"
    style="height: 400px; width: 100%"
    :scrollWheelZoom="false"
    :doubleClickZoom="false"
    :dragging="false"
    :touchZoom="false"
    :keyboard="false"
    :boxZoom="false"
    :zoomControl="false"
  >
    <LTileLayer :url="url" :attribution="attribution" />
    <LCircle :lat-lng="center" :radius="radius" color="blue" :fill-opacity="0.2" />
  </LMap>
</template>

<script>
import { LMap, LTileLayer, LCircle } from '@vue-leaflet/vue-leaflet'
import 'leaflet/dist/leaflet.css'
import L from 'leaflet'

// Import the icon images directly
import iconRetinaUrl from 'leaflet/dist/images/marker-icon-2x.png'
import iconUrl from 'leaflet/dist/images/marker-icon.png'
import shadowUrl from 'leaflet/dist/images/marker-shadow.png'

// Fix Leaflet's default icon not working
delete L.Icon.Default.prototype._getIconUrl
L.Icon.Default.mergeOptions({
  iconRetinaUrl,
  iconUrl,
  shadowUrl
})

export default {
  name: 'ServiceAreaMap',
  components: {
    LMap,
    LTileLayer,
    LCircle
  },
  data() {
    return {
      center: [42.755, -105.981], // Center between Wyoming and Nebraska
      zoom: 7, // Adjust the zoom level as needed
      radius: 250000, // Radius in meters (250 km)
      url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
      attribution: 'Map data © <a href="https://openstreetmap.org">OpenStreetMap</a> contributors'
    }
  }
}
</script>

<style scoped>
/* Add any additional styles here if needed */
</style>

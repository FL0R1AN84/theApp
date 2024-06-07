<template>
  <div ref="mapContainer" class="map-container"></div>
</template>

<script lang="ts" setup>
import { onMounted, ref } from 'vue'
import mapboxgl from 'mapbox-gl'

const mapContainer = ref(null)
const map = ref(null)

onMounted(() => {
  mapboxgl.accessToken =
    'pk.eyJ1IjoiZmwwcjFhbjg0IiwiYSI6ImNseDU4dHkyYzFjdG8ya3M0cWt5NHYxeTQifQ.BOPdowVpzfpSn6qox_-nWw'

  map.value = new mapboxgl.Map({
    container: mapContainer.value,
    style: 'mapbox://styles/mapbox/standard',
    center: [6.958735655501745, 50.94179850699188],
    zoom: 12
  })
})
</script>

<style scoped>
.map-container {
  width: 100%;
  height: 100vh;
}
</style>

<script setup>
import { ref, onMounted } from 'vue'
import L from 'leaflet'
import 'leaflet/dist/leaflet.css'

const map = ref(null)

const taiwanLocation = [23.6978, 120.9605]
const taiwanZoomin = 7

const initMap = () => {
  map.value = L.map('map').setView(taiwanLocation, taiwanZoomin)
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap contributors',
  }).addTo(map.value)
}

onMounted(() => {
  initMap()
})
</script>

<template>
  <div id="map" style="height: 400px"></div>
</template>

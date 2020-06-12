<template>
  
    <div style="height: 650px;">
        <div class="info" style="height: 15%">
            <span>Center: {{ center }} </span>
            <span> Zoom: {{ zoom }}</span>
        </div>
        <l-map
            style="height: 80%; width: 100%"
            :zoom="zoom"
            :center="center"
            @update:zoom="zoomUpdated"
            @update:center="centerUpdated"
            @update:bounds="boundsUpdated">

            <l-marker :lat-lng="markerLatLng1" :draggable="false" ></l-marker>
            <l-marker :lat-lng="markerLatLng2" :draggable="false" ></l-marker>

            <l-polyline :lat-lngs="getLatlngs()" :color="red"></l-polyline>

            <l-tile-layer :url="url"></l-tile-layer>
        </l-map>
    </div>

</template>

<script>
export default {
    data () {
        return {
            url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
            zoom: 6,
            center: [-36.633162, -57.249756],
            bounds: null,
            markerLatLng1: {
                lat: -34.706503,
                lng: -58.2790782
            },
            markerLatLng2: {
                lat: -38.005743,
                lng: -57.5734978
            }
        };
    },
    methods: {
        zoomUpdated (zoom) {
            this.zoom = zoom;
        },
        centerUpdated (center) {
            this.center = center;
        },
        boundsUpdated (bounds) {
            this.bounds = bounds;
        },
        getLatlngs () {
            return [[this.markerLatLng1.lat, this.markerLatLng1.lng], [this.markerLatLng2.lat, this.markerLatLng2.lng]]
        }
    }
}
</script>

<style>

</style>
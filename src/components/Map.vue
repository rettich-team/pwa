<template>
    <div style="height: 500px; width: 100%">
    <div style="height: 200px overflow: auto;">
      <button @click="showLongText">
        Toggle long popup
      </button>
    </div>
    <l-map
      v-if="showMap"
      :zoom="zoom"
      :center="center"
      :options="mapOptions"
      style="height: 80%"
      @update:center="centerUpdate"
      @update:zoom="zoomUpdate"
    >
      <l-tile-layer
        :url="url"
        :attribution="attribution"
      />
      <l-marker :lat-lng="withPopup">
        <l-popup>
          <div @click="innerClick">
            <v-card
              class="mx-auto"
              max-width="400"
            >
              <v-img
                class="white--text align-end"
                height="200px"
                src="./containern3.png"
              >
                <v-card-title>EDEKA Summerer</v-card-title>
              </v-img>

              <v-card-subtitle class="pb-0">ab 20 Uhr</v-card-subtitle>

              <v-card-text class="text--primary">
                <div>Links am Gebäude vorbeigehen...</div>
              </v-card-text>

              <v-card-actions>
            <v-btn block color="green" dark class="button">Status:<br>
             Heute noch nicht geleert!</v-btn>
              </v-card-actions>
            </v-card>
          </div>
        </l-popup>
      </l-marker>
    </l-map>
  </div>
</template>

<script>
import { latLng } from 'leaflet';
import {
  LMap, LTileLayer, LMarker, LPopup,
} from 'vue2-leaflet';

export default {
  name: 'Map',
  components: {
    LMap,
    LTileLayer,
    LMarker,
    LPopup,
  },
  data() {
    return {
      zoom: 13,
      center: latLng(47.41322, -1.219482),
      url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
      attribution:
        '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      withPopup: latLng(47.41322, -1.219482),
      withTooltip: latLng(47.41422, -1.250482),
      currentZoom: 11.5,
      currentCenter: latLng(47.41322, -1.219482),
      showParagraph: false,
      mapOptions: {
        zoomSnap: 0.5,
      },
      showMap: true,
    };
  },
  methods: {
    zoomUpdate(zoom) {
      this.currentZoom = zoom;
    },
    centerUpdate(center) {
      this.currentCenter = center;
    },
    showLongText() {
      this.showParagraph = !this.showParagraph;
    },
    innerClick() {
      alert('Click!');
    },
  },
};

</script>

<style scoped>

html, body, #app {
  height: 100%;
  margin: 0;
}
</style>

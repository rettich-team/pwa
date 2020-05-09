/* eslint-disable vue/no-parsing-error */
<template>

  <v-app>
    <v-card id="lateral">
    <v-toolbar
      dark
      fixed-tabs
      flat
      color="2f3618"
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-toolbar-title>Rettich</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
      <template v-slot:extension>
        <v-tabs
          fixed-tabs
          v-model="tabs"
        >
          <v-tab href="#one">Map</v-tab>
          <v-tab href="#two">List</v-tab>
          <v-tabs-slider color="d6fe75"></v-tabs-slider>
        </v-tabs>
      </template>
    </v-toolbar>
    <v-card-text>
      <v-tabs-items v-model="tabs">
        <v-tab-item
          v-for="content in ['one', 'two']"
          :key="content"
          :value="content"
        >
          <v-card
            height="100%"
            flat
          >
          <!-- card: -->
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
      <div>Links am Gebäude vorbeigehen. Dort befindet sich ein großer grüner Container!</div>
    </v-card-text>

    <v-card-actions>
  <v-btn block color="green" dark>Status: Heute noch nicht geleert!</v-btn>
    </v-card-actions>
  </v-card>
  <!-- card end -->
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-card-text>
    <v-fab-transition>
      <v-btn
        :key="activeFab.icon"
        :color="activeFab.color"
        fab
        large
        dark
        bottom
        left
        class="v-btn--example"
      >
        <v-icon>{{ activeFab.icon }}</v-icon>
      </v-btn>
    </v-fab-transition>
  </v-card>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  data: () => ({
    fab: false,
    hidden: false,
    tabs: null,
  }),

  computed: {
    // HelloWorld,
    activeFab() {
      switch (this.tabs) {
        case 'one': return { color: 'd3ff72', icon: 'mdi-plus' };
        case 'two': return { color: 'd3ff72', icon: 'mdi-crosshairs-gps' };
        default: return {};
      }
    },
  },
};
</script>

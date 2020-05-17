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
          v-model="tabs"
          grow
        >
          <v-tab>List</v-tab>
          <v-tab>Map</v-tab>
        </v-tabs>
      </template>
    </v-toolbar>
    <v-card-text>

      <v-tabs-items v-model="tabs">
        <v-tab-item>
        <BlogPost/>
      </v-tab-item>
      <v-tab-item>
        <p>Map comming soon</p>
      </v-tab-item>
        <v-tab-item
          v-for="content in ['one', 'two']"
          :key="content"
          :value="content"
        >
          <v-card
            height="100%"
            flat
          >
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
import BlogPost from './components/BlogPost.vue';

export default {
  name: 'App',
  components: {
    BlogPost,
  },
  data: () => ({
    fab: false,
    hidden: false,
    tabs: null,
  }),

  computed: {
    BlogPost,
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

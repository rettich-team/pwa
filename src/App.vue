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
      <v-btn icon @click="showInfo = !showInfo">
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-btn icon @click.native="showInfo = !showInfo">
        <v-icon>mdi-information</v-icon>
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

      <span v-if="showInfo"></span>
      <span v-else>
        <div style="height: 500px; width: 100%">
          <v-card color="#385F73" dark class="information">
                <v-card-title class="headline">Info</v-card-title>
                <iframe class="tabelle" width="95%" height="240" src="https://www.youtube.com/embed/3XcTwi3dKOM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <v-card-subtitle class="schrift">Weggeworfene Lebensmittel pro Kopf und Jahr:
                  </v-card-subtitle>
                  <v-simple-table class="tabelle">
                    <template v-slot:default>
                      <thead>
                        <tr>
                          <th class="text-left">Laender</th>
                          <th class="text-left">Kilogramm</th>
                        </tr>
                      </thead>
                      <tbody>
                        <tr v-for="item in laender" :key="item.name">
                          <td>{{ item.name }}</td>
                          <td>{{ item.kilogramm }}</td>
                        </tr>
                      </tbody>
                    </template>
                  </v-simple-table>

                <v-card-actions class="schliessen">
                  <v-btn @click.native="showInfo = !showInfo" text>Schließen</v-btn>
                </v-card-actions>
          </v-card>
        </div>
      </span>

    <v-card-text v-if="showInfo">
      <v-tabs-items v-model="tabs">
        <v-tab-item>
        <List/>
      </v-tab-item>
      <v-tab-item>
        <Map/>
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
  </v-card>
  </v-app>
</template>

<script>
import List from './components/List.vue';
import Map from './components/Map.vue';

export default {
  name: 'App',
  components: {
    List,
    Map,
  },
  data() {
    return {
      showInfo: true,
      fab: false,
      hidden: false,
      tabs: null,
      laender: [
        {
          name: 'USA, Kanada, Australien, Neuseeland',
          kilogramm: 296,
        },
        {
          name: 'Europa, Russland',
          kilogramm: 280,
        },
        {
          name: 'China, Japan, Südkorea',
          kilogramm: 236,
        },
        {
          name: 'Mittel- und Südamerika',
          kilogramm: 223,
        },
        {
          name: 'Nordafrika, Nord- und Zentralasien',
          kilogramm: 216,
        },
        {
          name: 'Afrika südlich der Sahara',
          kilogramm: 167,
        },
        {
          name: 'Süd- und Südostasien',
          kilogramm: 125,
        },
      ],
    };
  },


  computed: {
    List,
    activeFab() {
      switch (this.tabs) {
        case 'one': return { color: 'd3ff72', icon: 'mdi-plus' };
        case 'two': return { color: 'd3ff72', icon: 'mdi-crosshairs-gps' };
        default: return {};
      }
    },
  },
  toggleComponent() {
    this.component = this.component === List
      ? Map
      : List;
  },

};
</script>
<style scoped>
  .tabelle {
    margin: 10px;
    margin-bottom: 300px;
  }
  .schrift {
    margin-top: -280px;
    margin-bottom: -15px;
  }
  .schliessen {
    margin-top: -280px;
    margin-bottom: 400px;
  }
  .information {
    padding-bottom: 40px;
  }
</style>

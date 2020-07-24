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
        <div class="infocard" style="height: 500px; width: 100%">
          <v-card color="#385F73" dark class="information"><br>
            <v-card-actions class="schliessen">
                  <v-btn @click.native="showInfo = !showInfo" text>Schließen</v-btn>
                </v-card-actions>
                <v-card-title class="headline">Info</v-card-title>
                <v-expansion-panels focusable class="expansion">
                  <v-expansion-panel>
                    <v-expansion-panel-header>Video</v-expansion-panel-header>
                    <v-expansion-panel-content>
                      <iframe class="video" width="113%" height="240" src="https://www.youtube.com/embed/3XcTwi3dKOM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                    </v-expansion-panel-content>
                  </v-expansion-panel>
                  <v-expansion-panel>
                    <v-expansion-panel-header>Lebensmittelverschwendung
                    </v-expansion-panel-header>
                    <v-expansion-panel-content><br>
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
                    </v-expansion-panel-content>
                  </v-expansion-panel>
                  <v-expansion-panel>
                    <v-expansion-panel-header>Was ist Rettich?</v-expansion-panel-header>
                    <v-expansion-panel-content><br>
Rettich ist eine Ergänzung zu bestehen Lösungen wie https://foodsharing.de/ oder https://mundraub.org/
Eine Webapp, die das Containern (also das retten von Lebensmitteln die von den
 Supermärkten weggeschmissen werden aber noch gut sind) vereinfacht.
Also eine interaktive Map auf der die Spots angezeigt werden wo das Essen retten gut funktioniert.
Bei den Spots kann man dann den Status ändern, Kommentare hinzufügen oder den Spot bewerten.
 Es kann z.b. von “heute noch nicht geleert“ auf “hier gibt's leider nix mehr“
  geändert werden. Und wenn der Laden das nächste mal schließt wird das
 wieder automatisch auf "voll" resettet.
Zusätzlich kann man auch neue Spots mit kurzer Beschreibung
 eintragen und Fotos zu den Tonnen hinzufügen...
                    </v-expansion-panel-content>
                  </v-expansion-panel>
                  <v-expansion-panel>
                  <v-expansion-panel-header>was bringt das?</v-expansion-panel-header>
                    <v-expansion-panel-content><br>
                      Dank Rettich sparen sich die Essens-Retter zeit, Sie bringen
                       sich nicht unnötig in Gefahr und es vereinfacht ihnen das Leben.
Außerdem versuchen wir mit dieser provokanten Aktion das Thema Lebensmittel- Missbrauch
 in die Öffentlichkeit zu bringen und dafür zu sorgen, dass diesem
  Zustand mehr Aufmerksamkeit geschenkt wird!
wir kommerzialisieren quasi das Containern, wodurch es längerfristig vielleicht sogar legalisiert
 werden könnte oder noch besser es wird verboten noch gute Lebensmittel wegzuwerfen.
  Wenn weniger Lebensmittel weggeschmissen/produziert werden ist das ein Beitrag zum Klimaschutz.
Laut Schätzungen der Weltgesundheitsorganisation (WHO) werden weltweit rund 1,3 Milliarden Tonnen
 Lebensmittel pro Jahr verschwendet. Gleichzeitig müssen 821,6 Millionen Menschen hungern!
                    </v-expansion-panel-content>
                  </v-expansion-panel>
                  <v-expansion-panel>
                  <v-expansion-panel-header>Ist das Legal?</v-expansion-panel-header>
                    <v-expansion-panel-content><br>
                      Wir rufen nicht zu Straftaten auf,
                       sondern dokumentieren bloß die Erfahrungen anderer!
Das Containern selbst ist nach aktueller Rechtslage in Deutschland verboten und zählt als Diebstahl.
 Das ist ein Skandal und andere Länder Zeigen bereits wie es besser geht!
  Angesichts der immer weiter
  verschärfenden Klimakrise haltern wir es allerdings für Legitim diese Gesetze zu brechen.
                    </v-expansion-panel-content>
                  </v-expansion-panel>
                  <v-expansion-panel>
                  <v-expansion-panel-header>Wie geht man Containern?</v-expansion-panel-header>
                    <v-expansion-panel-content><br>
                      Alles was du brauchst ist eine Taschenlampe,
                       Handschuhe und ein Beutel für das Gerettete!
                    </v-expansion-panel-content>
                  </v-expansion-panel>
                  <v-expansion-panel>
                  <v-expansion-panel-header>Was wenn die Container verschlossen sind?
                  </v-expansion-panel-header>
                    <v-expansion-panel-content><br>
                      Das knacken der Container ist natürlich aufwendig. Aber wir haben gehört:
                       Da hilft Sekundenkleber. Einfach zukleben Dann müssen die
                        "Super"-märkte ihre Container selbst knacken und merken wie das ist.
                       Spätestens beim zweiten mal werden sie auch nicht mehr absperren!
                    </v-expansion-panel-content>
                  </v-expansion-panel>
                </v-expansion-panels>

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
    margin: 0px;
  }
  .schrift {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .schliessen {
    display: flex;
    justify-content: right;
    align-items: right;
    margin-left: 68%;
  }
  .information {
    padding-bottom: 500px;
  }
  .infocard {
    margin-top: -110px;
    padding-top: 0px;
  }
  .headline {
    margin-top: 0px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .expansion {
    margin: 10px;
    width: 95%;
  }
  .video {
    margin-bottom: -22px;
    margin-left: -23px;
  }
</style>

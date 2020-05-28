<template>
  <div class="list">
      <div id="cards" v-for="item in items" :key="item.message">
        <v-card
              class="mx-auto"
              max-width="400"
            >
              <v-img
                class="white--text align-end"
                height="200px"
                src="./containern3.png"
              >
                <v-card-title>{{ item.title }}</v-card-title>
              </v-img>

              <v-card-subtitle class="pb-0">ab {{ item.time }} Uhr</v-card-subtitle>

              <v-card-text class="text--primary">
                <div>{{ item.describtion }}</div>
              </v-card-text>

              <v-card-actions>
              <v-btn block color="green" dark class="button">Status:<br>
              {{ item.status }}</v-btn>
              </v-card-actions>
            </v-card>
      </div>
  </div>
</template>

<script>
// import Card from './card.vue';

export default {
  name: 'List',
  props: {
  },
  components: {
  },
  el: '#cards',
  data() {
    return {
      items: [
        {
          title: 'EdekaBla', time: '20', describtion: 'teilweise security unterwegs', status: 'heute noch nicht geleert!',
        },
        {
          title: 'Rewe Sowieso', time: '22', describtion: 'Links am Gebäude vorbeigehen..', status: 'hier gibts noch was',
        },
        {
          title: 'EdekaBla', time: '20', describtion: 'teilweise security unterwegs', status: 'heute noch nicht geleert!',
        },
        {
          title: 'Rewe Sowieso', time: '22', describtion: 'Links am Gebäude vorbeigehen..', status: 'leider schon leer',
        },
      ],
    };
  },
};
</script>

<style scoped>

.list {
  margin: 0px;
  max-width: 600px;
}
.button {
  width: 90%;
}
.mx-auto {
  margin-bottom: 20px;
}
</style>

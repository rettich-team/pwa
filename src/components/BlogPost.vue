<template>
  <div class="blogpost">
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
  <v-btn block color="green" dark class="button">Status:<br> Heute noch nicht geleert!</v-btn>
    </v-card-actions>
  </v-card>
  </div>
</template>

<script>
export default {
  name: 'BlogPost',
  props: {
  },
};
</script>

<style scoped>

.blogpost {
  margin: 0px;
  max-width: 600px;
}
.button {
  width: 90%;
}
</style>

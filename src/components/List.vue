<template>
  <div class="list">
  <card/>
  </div>
</template>

<script>
import Card from './card.vue';

export default {
  name: 'List',
  props: {
  },
  components: {
    Card,
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
</style>

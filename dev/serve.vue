<script lang="ts">
import Vue from 'vue';
import VScrollProgression from '@/v-scroll-progression.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    VScrollProgression
  }
});
</script>

<template>
  <div id="app">
    <v-scroll-progression />
  </div>
</template>

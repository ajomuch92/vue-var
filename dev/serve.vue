<script>
import Vue from 'vue';
import VueVar from '@/vue-var.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    VueVar
  }
});
</script>

<template>
  <div id="app">
    <vue-var />
  </div>
</template>

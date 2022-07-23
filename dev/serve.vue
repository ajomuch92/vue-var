<script>
import Vue from 'vue';
import VueVar from '@/vue-var.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    VueVar
  },
  data: () => ({
    items: [],
  }),
  created() {
    this.items = Array.from({length: 10}, (_, i) => i + 1);
  },
  methods: {
    myMethod(number) {
      return Math.pow(number, 2);
    }
  }
});
</script>

<template>
  <div id="app">
    <ul>
      <vue-var v-for="item in items" :key="item" :data="myMethod(item)">
        <li slot="default" slot-scope="{data}">
          Item {{item}} | My Method {{data}} | {{data % 2 == 0 ? 'Pair':'Odd'}}
        </li>
      </vue-var>
    </ul>
  </div>
</template>

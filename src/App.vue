<template>
  <div id="app">
    <v-btn @click="addCondition()" color="secondary" dark>Add Condition</v-btn>
    <div id="conditions">
      <template v-for="condition in conditions">
        <component :is="condition" :key="condition.id"></component>
      </template>
    </div>
  </div>
</template>

<script>
// none of the below work
//import Condition from '@/components/Condition.vue';
//const Condition = require('@/components/Condition.vue').default
Vue.component('Condition', require('@/components/Condition.vue').default);
import Vue from "vue";

export default {
  name: "Test",
  components:
  {
    Condition
  },
  methods: {
    addCondition()
    {
      const ConditionClass = Vue.extend(Condition);
      const conditionInstance = new ConditionClass(); //{ propsData: { id: conditions.length, value: 0 }});
      this.conditions.push(conditionInstance);
    }
  },
  data() {
    return {
      conditions: []
    };
  }
};
</script>

<style>
</style>

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
//import Condition from '@/components/Condition.vue';
const Condition = require('@/components/Condition.vue').default
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
      console.log("AC called");
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>

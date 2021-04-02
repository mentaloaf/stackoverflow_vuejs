<template>
  <div class="condition">
    <v-layout>
      <v-row>
        <v-col>
          <v-text-field label="Value" v-model="value"/>
        </v-col>
        <v-col>
          <v-text-field label="Min Value" v-model="minValue"/>
        </v-col>
        <v-col>
          <v-text-field label="Max Value" v-model="maxValue"/>
        </v-col>
      </v-row>
    </v-layout>
  </div>
</template>

<script>
export default {
  name: "Condition",
  /*
  props: {
    id: 0,
    value: 0,
  },
  */
  methods: {
    getValue: function() {
      return this.value;
    }
  },
  data() {
    return {
      id: 0,
      value: 0,
      minValue: 0,
      maxValue: 100
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

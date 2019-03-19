<template>
  <div>
    <fieldset>
      <legend>Formularz</legend>

      <input v-model="schema.title">
      <br>
      <select v-model="schema.type">
        <option v-for="stype in schemaTypes" :key="stype">{{stype}}</option>
      </select>
      <br>
      <p>properties</p>
      <br>

      <ul v-for="(property, nameOfProperty) in schema.properties" :key="property">
        <li>{{nameOfProperty}}</li>
      </ul>
    </fieldset>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  data() {
    return {
      schemaTypes: ['string', 'number', 'object', 'array', 'boolean', 'null']
    };
  },
  props: {
    schema: Object
  },
  computed: {}
});
</script>

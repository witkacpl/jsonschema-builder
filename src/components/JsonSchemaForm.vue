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
      <br>

      <ul v-for="(property, nameOfProperty) in schema.properties" :key="property">
        <li>{{nameOfProperty}}</li>

        <ul
          v-for="(propertyTwo, nameOfPropertyTwo) in schema.properties[nameOfProperty]"
          :key="propertyTwo"
        >
          <li>{{nameOfPropertyTwo}}</li>
          <input
            v-model="schema.properties[nameOfProperty][nameOfPropertyTwo]"
            v-if="schema.properties[nameOfProperty][nameOfPropertyTwo]!=='type'"
          >
          <p>{{schema.properties[nameOfProperty]}}</p>
          <!--<select v-if="check">
            <option v-for="stype in schemaTypes" :key="stype">{{stype}}</option>
          </select>-->
        </ul>
      </ul>
    </fieldset>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  data() {
    return {
      schemaTypes: ['string', 'number', 'object', 'array', 'boolean', 'null'],
      ifType: ''
    };
  },
  props: {
    schema: Object
  },
  computed: {}
});
</script>

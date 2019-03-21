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
      <ul>
        <li v-for="(property, propertyName, index) in schema.properties" :key="index">
          <div>
            <label>name:</label>
            {{propertyName}}
          </div>
          <button @click="deleteProperty(propertyName)">delete</button>
          <div>
            <label>data:</label>
            {{property}}
          </div>
          <div>
            <label>type:</label>
            <select v-model="property.type">
              <option v-for="stype in schemaTypes" :key="stype">{{stype}}</option>
            </select>
          </div>
          <div>
            <label>description:</label>
            <input v-model="property.description">
          </div>
        </li>
        <div>
          <br>
          <input v-model="newProperty">
          <button @click="addProperty()">add Property</button>
        </div>
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
      newProperty: ''
    };
  },
  props: {
    schema: Object
  },
  methods: {
    addProperty() {
      this.schema.properties[this.newProperty] = {};
      return (this.newProperty = '');
    },
    deleteProperty(e) {
      this.$delete(this.schema.properties, e);
    }
  }
});
</script>

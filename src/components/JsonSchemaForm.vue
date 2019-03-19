<template>
  <div>
    <fieldset>
      <legend>Formularz</legend>

      <input v-model="schema.title">
      <select v-model="schema.type">
        <option v-for="stype in schemaTypes" :key="stype">{{stype}}</option>
      </select>
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

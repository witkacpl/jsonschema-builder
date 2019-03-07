<template>
  <div>start
    <json-schema-form :schema="schema"></json-schema-form>
    <json-display :json="schema"></json-display>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import JsonDisplay from './components/JsonDisplay.vue';
import JsonSchemaForm from './components/JsonSchemaForm.vue';

const schema = require('./assets/assets.json');

export default Vue.extend({
  components: {JsonDisplay, JsonSchemaForm},
  data() {
    return {schema: schema};
  },
  mounted() {}
});
</script>


<style>
</style>

<template>
  <div>
    <fieldset>
      <legend>JSON</legend>
      {{stringified}}
    </fieldset>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  props: {
    json: Object
  },
  computed: {
    stringified(): string {
      if (!this.json) {
        return 'Źródło jest puste!';
      }
      return JSON.stringify(this.json);
    }
  }
});
</script>

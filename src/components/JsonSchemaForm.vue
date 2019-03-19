<template>
  <div>
    <fieldset>
      <legend>To formularz</legend>
      {{schema}}
    </fieldset>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  props: {
    schema: Object
  },
  computed: {}
});
</script>

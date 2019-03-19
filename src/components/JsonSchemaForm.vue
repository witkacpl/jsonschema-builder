<template>
  <div>
    <fieldset>
      <legend>Czy dziala</legend>

      <input v-model="schema.title"></input>
      <!--<select v-model="schema.type" >
		    <option v-for='(n,nr) in mainType'>{{nr}}</option>
	    </select>
      -->

    </fieldset>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  props: {
    schema: Object
  },
  //data:{
  //  mainType=['string', 'number']
 // },
  computed: {}
});
</script>

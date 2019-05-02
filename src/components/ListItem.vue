<template lang="html">
  <option v-on:click="handleClick" :value="country">{{country.name}}</option>
</template>

<script>
import{eventBus} from "../main.js";

export default {
  name: 'list-item',
  props: ['country'],
  methods:{
    handleClick(){
      console.log("click", this.country.name);
      eventBus.$emit('viewitem', this.country);
    }
  }
};
</script>

<style lang="css" scoped>
</style>

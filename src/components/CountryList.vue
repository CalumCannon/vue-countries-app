<template lang="html">
  <div>
    <select v-on:change="handleClick" v-model="selectedCountry">
      <list-item v-for="(country, index) in countries" :country="country" :key="index" > </list-item>
    </select>
  </div>
</template>

<script>
import ListItem from './ListItem.vue';
import{eventBus} from "../main.js";

export default {
  name: 'country-list',
  data(){
    return{
      selectedCountry: null,
    }
  },
  props: ['countries'],
  methods:{
    handleClick(){
      eventBus.$emit('viewitem', this.selectedCountry);
    }
  },
  components:{
    "list-item" : ListItem
  }
}
</script>

<style lang="css" scoped>
</style>

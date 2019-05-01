<template>
  <div id="app">
    <country-list :countries="countries"></country-list>
    <country-detail :country="selectedCountry"></country-detail>
  </div>
</template>

<script>
import CountryList from './components/CountryList.vue';
import CountryDetail from './components/CountryDetail.vue';
import {eventBus} from './main.js';
export default {
  name: 'app',
  data(){
    return{
      countries: [],
      selectedCountry: null
    };

  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)

    eventBus.$on('viewitem', (country) => {

      this.selectedCountry = country;
        console.log(this.selectedCountry);
    })
  },
  components: {
    'country-list': CountryList,
    'country-detail' : CountryDetail,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

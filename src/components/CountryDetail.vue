<template lang="html">
<div v-if="country">
  <p>{{country.name}}</p>
  <p>Population: {{country.population}}</p>
  <p>Capital: {{country.capital}}</p>
  <p>Spoken Languages</p>
  <p v-for="(lang, index) in country.languages" > {{lang.name}} </p>
</div>
</template>

<script>
export default {
  name: "country-detail",
  props: ["country"]

}
</script>

<style lang="css" scoped>
</style>

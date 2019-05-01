<template lang="html">
<div v-if="country">
  <p>{{country.name}}</p>
  <p>{{country.population}}</p>
  <p>{{country.capital}}</p>
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

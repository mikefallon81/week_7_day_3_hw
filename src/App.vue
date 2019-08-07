<template lang="html">
  <div>
    <h1>Countries</h1>
    <div>
      <country-list :countries='countries'></country-list>
    </div>
  </div>
</template>

<script>
import CountryList from './components/CountryList.vue';
import CountryDetail from './components/CountryDetail.vue';

export default {
  name: 'app',
  data() {
    return {
      countries: []
    };
  },
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
      .then(res => res.json())
      .then(countries => this.countries = countries)
  },
  components: {
    "country-list": CountryList
  }
}
</script>

<style lang="css" scoped>
</style>

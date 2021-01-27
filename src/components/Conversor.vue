<template>
  <div class='conversor'>
    <h2>{{currencyFrom}} para {{currencyTo}}</h2>
    <input type="text" v-bind:placeholder="currencyFrom" v-model="currencyFrom_value">
    <input type="button" value="Converter" v-on:click="converter">
    <h2>{{currencyTo_value}}</h2>
  </div>
</template>

<script>
export default {
  name: 'Conversor',
  props: ['currencyFrom', 'currencyTo'],
  data() {
    return {
      currencyFrom_value: '',
      currencyTo_value: 0
    };
  },

  methods: {
    converter() {
      let from_to = this.currencyFrom + '_' + this.currencyTo;
      let url = 'https://free.currconv.com/api/v7/convert?q=' + from_to + '&ompact=ultra&apiKey=' + process.env.VUE_APP_FREE_CURR_CONV_KEY;

      fetch(url)
        .then(response => response.json())
        .then(json => {
          let cotacao = json.results[from_to].val;

          this.currencyTo_value = (parseFloat(this.currencyFrom_value) * cotacao).toFixed(2);
        });
    }
  }
}
</script>

<style scoped>
  .conversor {
    max-width: 300px;
    padding: 20px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  }
</style>
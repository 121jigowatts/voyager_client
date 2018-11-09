<template>
  <div>
    <p>
      ここはページ２です。
    </p>
    <p>
      <router-link to="/HelloWorld">Go to Hello World</router-link>
    </p>
    <p>
      <router-link to="/">Go to page1</router-link>
    </p>
    <h1>Bitcoin Price Index</h1>
    <div v-for="currency in info" :key="currency.code"
    class="currency">
      {{currency.description}}
      <span class="lighten">
        <span v-html="currency.symbol"></span>
        {{ currency.rate_float | currencydecimal }}
      </span>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      info: null
    };
  },
  mounted() {
    axios
      .get("https://api.coindesk.com/v1/bpi/currentprice.json")
      .then(response => (this.info = response.data.bpi));
  },
  filters: {
    currencydecimal(value) {
      return value.toFixed(2);
    }
  }
};
</script>

<style>
</style>
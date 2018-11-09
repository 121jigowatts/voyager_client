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
    <div>
      {{ info }}
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      info: null
    };
  },
  mounted() {
    axios
      .get("https://api.coindesk.com/v1/bpi/currentprice.json")
      .then(response => (this.info = response));
  }
}
</script>

<style>
</style>
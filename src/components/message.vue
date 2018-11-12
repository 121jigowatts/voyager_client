<template>
  <div>
    <h1>Messages</h1>
    <table>
      <tr>
        <th>ID</th>
        <th>TEXT</th>
        <th>DATE</th>
      </tr>
      <tr v-for="message in info" :key="message.id"
        class="message">
        <td>{{message.id}}</td>
        <td>{{message.text}}</td>
        <td>{{message.stringDate}}</td>
      </tr>
    </table>
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
      .get("http://localhost:8080/api/messages")
      .then(response => (this.info = response.data));
  }
};
</script>

<style>
</style>
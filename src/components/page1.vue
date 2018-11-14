<template>
  <div>
    <p>
      ここはページ１です。
    </p>
    <p>
      <router-link to="/HelloWorld">Go to Hello World</router-link>
    </p>
    <p>
      <router-link to="/page2">Go to page2</router-link>
    </p>
    <p v-if="message.length > 0">
      {{message}}
    </p>
    <p v-else>
      no text
    </p>
    <input v-model="message">
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'test'
    };
  }
};
</script>

<style>
</style>
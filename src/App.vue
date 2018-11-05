<template>
  <div id="app">
    <itsheader></itsheader>
    <p v-if="msg.length > 0">
      {{msg}}
    </p>
    <p v-else>
      no text
    </p>
    <input type="text" v-model="msg">
    <button @click="clear()">clear</button>
  </div>
</template>

<script>
import itsheader from './components/itsheader'

export default {
  components: {
    itsheader
  },
  data() {
    return {
      msg: 'hello world!'
    }
  },
  methods: {
    clear () {
      this.msg = ''
    }
  }
}
</script>

<template>
  <div id="app">
    <HelloWorld v-bind:title="message" v-bind:num="num" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      message: 'computed',
      num: 90
    }
  },
}
</script>

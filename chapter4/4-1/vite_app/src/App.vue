<template>
  <div id="app">
    <HelloJSX title="OK, Vue3" msg="message specified by attribute" />
  </div>
</template>

<script>
import HelloJSX from './components/HelloJSX.jsx'

export default {
  name: 'App',
  components: {
    HelloJSX
  }
}
</script>

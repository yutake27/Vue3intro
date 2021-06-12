<template>
  <div class="alert alert-primary">
    <h2>{{ title }}</h2>
    <pre>{{ message }}</pre>
    <hr>
    <div class="area"
      v-on:click.left.prevent="left"
      v-on:click.middle.prevent="middle"
      v-on:click.right.prevent="right">
        click hare!
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function() {
    return {
      title: 'Event',
      message: ''
    }
  },
  methods: {
    left() {
      this.message = '[left button]'
    },
    middle() {
      this.message = '[middle button]'
    },
    right() {
      this.message = '[right button]'
    }
  },
}
</script>

<style>
pre {
  font-size: 16pt;
  line-height: 1.25;
}
.area {
  width: 300px;
  height: 100px;
  background-color: #fff;
  padding: 10px;
  font-size: 20pt;
}
</style>


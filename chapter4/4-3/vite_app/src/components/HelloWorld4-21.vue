<template>
  <div class="alert alert-primary">
    <h2>{{ title }}</h2>
    <pre>{{ message }}</pre>
    <hr>
    <div class="area"
      v-on:click="click"
      v-on:click.exact="exact"
      v-on:click.shift="shift"
      v-on:click.ctrl="ctrl"
      v-on:click.alt="alt">
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
    click() {
      this.message = 'click '
    },
    exact() {
      this.message += '**no any key**'
    },
    shift() {
      this.message += '[Shift]'
    },
    ctrl() {
      this.message += '[ctrl]'
    },
    alt() {
      this.message += '[alt]'
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


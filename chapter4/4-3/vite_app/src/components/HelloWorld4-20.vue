<template>
  <div class="alert alert-primary">
    <h2>{{ title }}</h2>
    <pre v-on:click="clear">{{ message }}</pre>
    <hr>
    <div>
      <input type="text" class="form-control"
       v-on:keypress="type"
       v-on:keydown.delete="clear"
       v-on:keydown.space="space"
       v-on:keydown.enter="enter">
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
    type(event) {
      if (event.key == "Enter"){ return }
      this.message += event.key+ ' '
      event.target.value = ''
    },
    clear() {
      this.message = ''
    },
    space() {
      this.message += '_ '
    },
    enter(event) {
      var res = this.message.split(' ').join('')
      this.message = res.split('_').join(' ')
      event.target.value = ''
    }
  },
}
</script>

<style>
pre {
  font-size: 16pt;
  line-height: 1.25;
}
div.out {
  padding: 0px;
  background-color: #eee;
  width: 300px;
  height: 200px;
}
div.mid {
  padding: 0px;
  background-color: #ddd;
  width: 200px;
  height: 170px;
}
div.in {
  padding: 0px;
  background-color: #ccc;
  width: 100px;
  height: 140px;
}
</style>


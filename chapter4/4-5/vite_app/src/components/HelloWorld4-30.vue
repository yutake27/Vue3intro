<template>
  <div class="alert alert-primary">
    <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <button class="btn btn-primary m-3" v-on:click="doAction">
      {{ btn }}
    </button>
    <transition name="transit">
      <p v-if="flg" class="alert p-3 h5 trans">
        Transition context!
      </p>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      title: 'Trans&Anim',
      message: "This is Transition sample!",
      flg: true,
      btn: 'Show/Hide'
    }
  },
  methods: {
    doAction() {
      this.flg = !this.flg
    }
  },
}
</script>

<style>
.trans {
  background-color: black;
  color: white;
  padding: 10px;
  font-size: 20pt;
}

.transit-enter-active {
  transition: opacity 0.5s;
}
.transit-leave-active {
  transition: opacity 5.0s;
}
.transit-enter {
  opacity: 0;
}
/* .transit-enter-from {
  opacity: 0;
} */
.transit-enter-to {
  opacity: 1.0;
}
.transit-leave {
  opacity: 1.0;
}
.transit-leave-to {
  opacity: 0;
}
</style>
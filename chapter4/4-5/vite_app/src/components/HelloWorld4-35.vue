<template>
  <div class="alert alert-primary">
    <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <button class="btn btn-primary m-3" v-on:click="doAction">
      Show/Hide
    </button>
    <transition name="transit">
      <p v-if="flg" class="trans">Transition!</p>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      title: 'Trans & Anim',
      message: "This is Transition sample!",
      flg: true,
      btn: 'Hide',
    }
  },
  methods: {
    doAction() {
      this.flg = !this.flg
    },
  },
}
</script>

<style>
.transit-enter-active{
  transition: 1.0s;
}
.transit-leave-active {
  transition: 1.0s;
  opacity: 0.5;
}
.trans {
  background-color: black;
  color: white;
  padding: 10px;
  font-size: 20pt;
}

.transit-enter, .transit-leave-to {
  transform: rotateZ(360deg);
  opacity: 0.1;
}
</style>
<template>
  <div class="alert alert-primary">
    <h2>{{ title }}</h2>
    <p>{{ message }}</p>
    <hr>
    <div class="alert alert-light">
      <h3>Inner slot</h3>
      <ol class="list-group text-left">
        <slot />
      </ol>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function() {
    return {
      title: 'Slot',
      message: 'This is message.',
    }
  }
}
</script>

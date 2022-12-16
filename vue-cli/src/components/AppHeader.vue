<template>
  <header>
    <h1>{{ propsdata }}</h1>
    <button v-on:click="sendEvent">send</button>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  props: {
    propsdata: {},
  },
  methods: {
    sendEvent(){
      this.$emit('emitTest');
    }
  }
}
</script>

<style scoped>

</style>
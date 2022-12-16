<template>
  <form v-on:submit="submitForm">
    <div>
      <label for="username">id: </label>
      <input id="username" type="text" v-model="username">
    </div>
    <div>
      <label for="password">pw: </label>
      <input id="password" type="password" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
    };
  },
  methods: {
    submitForm(event){
      event.preventDefault();   // submit은 기본적으로 새로고침 기능이 있음. 그걸 막아주는 event 함수
      console.log(this.username + ", " + this.password);
    }
  },
}
</script>

<style>

</style>

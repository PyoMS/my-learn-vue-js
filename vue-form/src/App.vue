<template>
  <form v-on:submit.prevent="submitForm">
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
import axios from 'axios';

export default {
  data() {
    return {
      username: '',
      password: '',
    };
  },
  methods: {
    submitForm(){
      // event.preventDefault();   // submit은 기본적으로 새로고침 기능이 있음. 그걸 막아주는 event 함수
      console.log(this.username + ", " + this.password);
      var url = "https://jsonplaceholder.typicode.com/users";
      var data = {
        username : this.username,
        password : this.password,
      }
      axios.post(url, data)
          .then(function (response){
            console.log(response)
          })
          .catch(function (error){
            console.log(error);
          });
    }
  },
}
</script>

<style>

</style>

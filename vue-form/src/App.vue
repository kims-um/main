<template>
  <form v-on:submit.prevent="subForm">
    <div>
      <label for="username">id:</label>
      <input type="text" id="username" v-model="username" />
    </div>
    <div>
      <label for="password">pw:</label>
      <input id="password" type="text" v-model="password" />
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
  import axios from "axios";

  export default {
    data: function() {
      return {
        username: "",
        password: "",
      };
    },
    methods: {
      subForm: function() {
        console.log(this.username, this.password);
        let url = "https://jsonplaceholder.typicode.com/users/";
        let data = {
          username: this.username,
          password: this.password,
        }
      },
      axios.post(url, data);
        .then(function(response){
          console.log(response);
        })
        .catch(function(error) {
          console.log(error);
        })
  };
</script>

<style></style>

<template>
  <div>
    <form v-on:submit.prevent="login">
      <user-name-input v-on:pass="setUserName"></user-name-input>
      <password-input v-on:pass="setPassword"></password-input>
      <button type="submit">login</button>
    </form>
  </div>
</template>

<script>
import UserNameInput from "@/components/section12/UserNameInput.vue";
import PasswordInput from "@/components/section12/PasswordInput.vue";

export default {
  components: {PasswordInput, UserNameInput}
  , data: function () {
    return {
      username: ""
      , password: ""
    }
  }
  , methods: {
    login: function () {
      const url = "https://jsonplaceholder.typicode.com/users";
      const data = {
        username: this.username
        , password: this.password
      };

      axios.post(url, data)
          .then((response) => {
            console.log(response);
          })
          .catch(error => {
            console.log(error);
          })
    }
    , setUserName: function (username) {
      this.username = username;
    }
    , setPassword: function (password) {
      this.password = password;
    }
  }
};
</script>
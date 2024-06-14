<template>
  <div>
    <label for="username">id : </label>
    <input id="username" v-model="username" type="text" v-on:keyup="setUserName"/>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      username: ""
    }
  }
  , methods: {
    setUserName: function () {
      this.$emit('pass', this.username)
    }
  }
};
</script>
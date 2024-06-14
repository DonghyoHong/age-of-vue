<template>
  <div>
    <label for="password">pw : </label>
    <input id="password" v-model="password" type="password" v-on:keyup.prevent="getPassword"/>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      password: ""
    }
  }
  , methods: {
    getPassword: function () {
      this.$emit('pass', this.password);
    }
  }
};
</script>
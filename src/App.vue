<script>
import {defineComponent} from "vue";
import HelloWorld from "@/components/HelloWorld.vue";
import TheWelcome from "@/components/TheWelcome.vue";
import EventEmit from "@/components/EventEmit.vue";

export default defineComponent({
  data: function () {
    return {
      num: 0
    }
  }
  , components: {
    EventEmit
    , TheWelcome
    , HelloWorld
  }
  , methods: {
    addNumber: function () {
      this.num++;
      console.log(this.num);
    }
  }
})


</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" height="125" src="./assets/logo.svg" width="125"/>
    <div class="wrapper">
      <HelloWorld msg="Hello"></HelloWorld>
      <EventEmit v-on:pass="addNumber"></EventEmit>
      <p>{{ num }}</p>
    </div>
  </header>

  <main>
    <!--    <TheWelcome></TheWelcome>-->
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>

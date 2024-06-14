<script>
import {defineComponent} from "vue";
import EventEmit from "@/components/EventEmit.vue";
import AppHeader from "@/components/AppHeader.vue";

export default defineComponent({
  data: function () {
    return {
      num: 0
    }
  }
  , components: {
    EventEmit
    , AppHeader
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
    <div>
      <AppHeader header="App Header"></AppHeader>
      <div>
        <p>Event Emit</p>
        <EventEmit v-on:pass="addNumber"></EventEmit>
        <p>{{ num }}</p>
      </div>
    </div>
  </header>

  <main>
    <!--    <TheWelcome></TheWelcome>-->
  </main>
</template>

<style>
</style>

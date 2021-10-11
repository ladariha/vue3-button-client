<template>
  <div id="app">
    <MyButton />
    Reactive number: {{ randomNumber }}
  </div>
</template>

<script lang="ts">
import MyButton from "ladariha-button/src/components/MyButton.vue";
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "App",
  components: {
    MyButton,
  },
  setup() {
    const randomNumber = ref(Math.random());

    setInterval(() => {
      randomNumber.value = Math.random();
    }, 3000);

    return { randomNumber };
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
  <div id="app">
    <h1>Button from Vue3</h1>
    <MyButton />
    <h1>Button from Vue2</h1>
    <MyButton2 />
    Reactive number: {{ randomNumber }}
  </div>
</template>

<script lang="ts">
import MyButton from "ladariha-button/src/components/MyButton.vue";
import MyButton2 from "ladariha-button-2/src/components/MyButton.vue";
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "App",
  components: {
    MyButton,
    MyButton2,
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

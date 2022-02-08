<template>
  <div id="app">
    <h1>Algorithms testing page</h1>
    <input v-model.number="repeat" placeholder="Введите количество повторений">
    <p>Количество повторений: {{ repeat }}</p>
    <div>
      <button
          v-for="tab in tabs"
          v-bind:key="tab"
          v-bind:class="['tab-button', { active: currentTab === tab }]"
          v-on:click="currentTab = tab"
        >{{ tab }}</button>
      <p>Выбранный режим: {{ currentTab }}</p>
      <component v-bind:is="currentTab" v-bind:repeats="repeat" class="tab"></component>
    </div>
  </div>
</template>

<script>

import EasyOneTwo from "./components/EasyOneTwo.vue";
import EasyOneThree from "./components/EasyOneThree.vue";
import EasyOneFour from "./components/EasyOneFour.vue";
import EasyOneFive from "./components/EasyOneFive.vue";
import EasyOneSix from "./components/EasyOneSix.vue";
import EasyOneSeven from "./components/EasyOneSeven.vue";
import EasyOneEight from "./components/EasyOneEight.vue";
import EasyOneNine from "./components/EasyOneNine.vue";


export default {
  name: 'App',
  data: function () {
    return {
      currentTab: "EasyOneTwo",
      tabs: ["EasyOneTwo", "EasyOneThree", "EasyOneFour", "EasyOneFive", "EasyOneSix", "EasyOneSeven", "EasyOneEight", "EasyOneNine"],
      repeat: 0
    }
  },
  components: {
    EasyOneTwo, EasyOneThree, EasyOneFour, EasyOneFive, EasyOneSix, EasyOneSeven, EasyOneEight, EasyOneNine
  }
}
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

button {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin-right: 1%;
}

input {
  width: 50%;
  padding: 12px 20px;
  margin: 8px 0;
  box-sizing: border-box;
}
</style>

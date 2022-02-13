<template>
  <div id="app">
    <h1>Algorithms testing page</h1>
    <div>
      <!-- Running algorithm by pressing on button. Passing the value to selected component -->
      <component v-bind:is="currentTab" v-bind:repeats="repeat" class="tab"></component>
    </div>
  </div>
</template>

<script>

//Components import
import AlgorithmsUI from "@/components/AlgorithmsUI.vue";

export default {
  name: 'App',
  data: function () {
    return {
      currentTab: "AlgorithmsUI",
      repeat: 0
    }
  },
  components: { AlgorithmsUI }
}
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    font-size: 24px;
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
    margin-bottom: 1%;
  }

  input {
    width: 50%;
    padding: 12px 20px;
    margin: 8px 0;
    box-sizing: border-box;
  }
</style>

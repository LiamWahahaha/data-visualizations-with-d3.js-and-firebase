<template>
  <div id="app">
    <!-- <UsingArrowFunction/> -->
    <!-- <JoiningDataToMultipleElements/> -->
    <!-- <TheEnterSelection/> -->
    <D3Circle/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
// import UsingArrowFunction from './components/UsingArrowFunction.vue';
// import JoiningDataToMultipleElements from './components/JoiningDataToMultipleElements.vue';
// import TheEnterSelection from './components/TheEnterSelection.vue';
import D3Circle from './components/D3Circle.vue';
@Component({
  components: {
    // UsingArrowFunction,
    // JoiningDataToMultipleElements,
    // TheEnterSelection,
    D3Circle,
  },
})
export default class App extends Vue {}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

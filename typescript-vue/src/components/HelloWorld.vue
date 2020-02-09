<template>
  <div>
    {{ msg }}
    <svg></svg>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import * as d3 from 'd3';

@Component
export default class HelloWorld extends Vue {
  // private list: Array<object> = [{
  //   name: "Lorem",
  //   total: 30
  // }, {
  //   name: "Ipsum",
  //   total: 21
  // }, {
  //   name: "Dolor",
  //   total: 20
  // }]
  private data: number[] = [99, 71, 78, 25, 36, 92];
  // @Prop() private msg!: string;
  private msg: string = 'Hello World';

  public mounted() {
    const svg = d3.select('svg')
      .attr('width', 500)
      .attr('height', 270);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
svg {
  margin: 25px;
  path {
    fill: none;
    stroke: #76bf8a;
    stroke-width: 3px;
  }
}
</style>

<template>
  <div class="canvas">
    <svg width="600" height="600">
      <rect></rect>
      <rect></rect>
      <rect></rect>
    </svg>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import * as d3 from 'd3';

@Component
export default class UsingDataWithD3 extends Vue {
  private data: any[] = [
    {
      width: 200,
      height: 100,
      fill: 'purple',
    },
    {
      width: 100,
      height: 60,
      fill: 'pink',
    },
    {
      width: 50,
      height: 30,
      fill: 'red',
    },
  ];

  public mounted() {
    const svg = d3.select('svg');

    const rect  = svg.selectAll('rect')
      .data(this.data)
      .attr('width', (d, i, n) => d.width)
      .attr('height', (d, i, n) => d.height)
      .attr('fill', (d, i, n) => d.fill);
  }
}
</script>
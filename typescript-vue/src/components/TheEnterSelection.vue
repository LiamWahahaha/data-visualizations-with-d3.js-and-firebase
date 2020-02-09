<template>
  <div class="canvas">
    <svg width="600" height="600">
      <rect></rect>
    </svg>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import * as d3 from 'd3';

interface RectAttrs {
  width: number;
  height: number;
  fill: string;
}

@Component
export default class UsingDataWithD3 extends Vue {
  private data: RectAttrs[] = [
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

    // Join data to rects
    const rects = svg.selectAll('rect')
      .data(this.data);

    // add attrs to rects already in the DOM
    rects.attr('width', (d, i, n) => d.width)
      .attr('height', (d, i, n) => d.height)
      .attr('fill', (d, i, n) => d.fill);

    // append the enter selection to DOM
    rects.enter()
      .append('rect')
      .attr('width', (d, i, n) => d.width)
      .attr('height', (d, i, n) => d.height)
      .attr('fill', (d, i, n) => d.fill);
  }
}
</script>
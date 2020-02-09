<template>
  <div class="canvas">
    <svg width="600" height="600">
      <rect class="arrow"></rect>
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
  ];

  public mounted() {
    const svg = d3.select('rect.arrow');

    svg
      .data(this.data)
      .attr('width', (d) => d.width)
      .attr('height', (d) => d.height)
      .attr('fill', (d) => d.fill);
  }
}
</script>
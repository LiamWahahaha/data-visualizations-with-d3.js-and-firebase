<template>
  <div class="canvas">
    <svg width="600" height="600">
      <circle/>
    </svg>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import * as d3 from 'd3';

interface CircleAttrs {
  radius: number;
  distance: number;
  fill: string;
}

@Component
export default class UsingDataWithD3 extends Vue {
  private data: CircleAttrs[] = [
    {
      radius: 50,
      distance: 110,
      fill: 'orange',
    },
    {
      radius: 70,
      distance: 260,
      fill: 'red',
    },
    {
      radius: 35,
      distance: 400,
      fill: 'brown',
    },
    {
      radius: 55,
      distance: 530,
      fill: 'green',
    },
  ];

  public mounted() {
    // select svg container first
    const svg = d3.select('svg');

    const circs = svg.selectAll('circle')
      .data(this.data);

    // add attrs to circs already in the DOM
    circs.attr('cy', 200)
      .attr('cx', (d) => d.distance)
      .attr('r', (d) => d.radius)
      .attr('fill', (d) => d.fill);

    // append the enter selection to DOM
    circs.enter()
      .append('circle')
      .attr('cy', 200)
      .attr('cx', (d) => d.distance)
      .attr('r', (d) => d.radius)
      .attr('fill', (d) => d.fill);
  }
}
</script>
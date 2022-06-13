<script>
  // import { hsl } from 'd3-color';
  // import { interpolateNumber } from 'd3-interpolate';
  // import { scaleLinear } from 'd3-scale';
  import { scaleLinear } from 'd3';

  // const c = hsl('steelblue');
  // c.h += 90;
  // c.s += 0.2;
  // const color = c + '';

  // const i = interpolateNumber(10, 20);

  const x = scaleLinear()
    .domain([10, 130])
    .range([0, 960]);
</script>

<!-- <h1>{ color }</h1> -->
<!-- <h1>{ i(0.2) }</h1> -->
<h1>{ x(50) }</h1>
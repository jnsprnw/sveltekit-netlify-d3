<script>
  import { scaleLinear } from 'd3-scale';

  const x = scaleLinear()
    .domain([10, 130])
    .range([0, 960]);
</script>

<h1>{ x(50) }</h1>

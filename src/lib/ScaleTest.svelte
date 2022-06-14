<script>
	import { scaleLinear } from 'd3-scale';

	let width = 50;

	$: x = scaleLinear()
    .domain([0, 1])
    .range([0, width]);
</script>

<h1 bind:clientWidth={width}>{ x(0.5) }</h1>
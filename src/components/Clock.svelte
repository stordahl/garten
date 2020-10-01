<script>
	import { onMount } from 'svelte';
	let date = new Date();
	$: hour = date.getHours();
	$: min = date.getMinutes();
	$: sec = date.getSeconds();
	let dayOrNight = 'AM';
	
	onMount( () => {
		const interval = setInterval(() => {
			date = new Date();
			dayOrNight = (hour >= 12) ? "PM" : "AM";
		}, 1000);
	});
</script>

<style>
	.clockDisplay {
		display: flex;
		justify-content: center;
        align-items: center;
        position:absolute;
        bottom: 0;
        left:50%;
        transform:translateX(-50%);
	}
	
	
	
</style>


		<h6 class='clockDisplay'> 
			{#if hour > 12}
				{hour - 12}
			{:else}
				{hour}
			{/if} : {min} : {sec} {dayOrNight}
		</h6>
	









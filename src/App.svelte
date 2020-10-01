<script>
	import Center from './components/Center.svelte';
	import Clock from './components/Clock.svelte';
	import Projects from './components/Projects.svelte';
	import Circle from './components/Circle.svelte';
	import Wtf from  './components/Wtf.svelte';
	import { onMount } from 'svelte';

	const info = {
		twitter: 'queeryselector',
		insta: 'queeryselector',
		github: 'stordahl',
		resume: 'https://stordahl.dev',
		name: 'jacob stordahl'
	};
	const circle = {
		text: 'the world may be on fire, but atleast we have the internet...',
		width:600,
		height:600,
		viewbox: '0 0 600 600',

	};
	const lat = '44.9778° N, 93.2650° W';

	let bgClasses = ['default', 'pink', 'blue', 'salmon'];

	onMount( () => {
		let rand = bgClasses[Math.floor(Math.random() * bgClasses.length)];
		window.document.body.classList.toggle(rand);
	});
</script>

	<h6 id="lat">{ lat }</h6>

	<Wtf />
	<main>
		<Center {...info}/>
	</main>
	
	<Projects />
	<Clock />
	
	<Circle {...circle}/>

<style>
	:global(body.default) {
		background: hsla(298, 68%, 90%, 1);
		background: linear-gradient(180deg, hsla(298, 68%, 90%, 1) 0%, hsla(30, 82%, 91%, 1) 100%);
		background: -moz-linear-gradient(180deg, hsla(298, 68%, 90%, 1) 0%, hsla(30, 82%, 91%, 1) 100%);
		background: -webkit-linear-gradient(180deg, hsla(298, 68%, 90%, 1) 0%, hsla(30, 82%, 91%, 1) 100%);
		filter: progid: DXImageTransform.Microsoft.gradient( startColorstr="#f6d5f7", endColorstr="#fbe9d7", GradientType=1 );
	}
	:global(body.pink){
		background: hsla(332, 53%, 82%, 1);
		background: linear-gradient(90deg, hsla(332, 53%, 82%, 1) 0%, hsla(176, 57%, 89%, 1) 100%);
		background: -moz-linear-gradient(90deg, hsla(332, 53%, 82%, 1) 0%, hsla(176, 57%, 89%, 1) 100%);
		background: -webkit-linear-gradient(90deg, hsla(332, 53%, 82%, 1) 0%, hsla(176, 57%, 89%, 1) 100%);
		filter: progid: DXImageTransform.Microsoft.gradient( startColorstr="#E9B7CE", endColorstr="#D3F3F1", GradientType=1 );
	}
	:global(body.blue){
		background: hsla(18, 76%, 85%, 1);
		background: linear-gradient(90deg, hsla(18, 76%, 85%, 1) 0%, hsla(203, 69%, 84%, 1) 100%);
		background: -moz-linear-gradient(90deg, hsla(18, 76%, 85%, 1) 0%, hsla(203, 69%, 84%, 1) 100%);
		background: -webkit-linear-gradient(90deg, hsla(18, 76%, 85%, 1) 0%, hsla(203, 69%, 84%, 1) 100%);
		filter: progid: DXImageTransform.Microsoft.gradient( startColorstr="#F6CFBE", endColorstr="#B9DCF2", GradientType=1 );
	}
	:global(body.salmon){
		background: hsla(0, 87%, 79%, 1);
		background: linear-gradient(90deg, hsla(0, 87%, 79%, 1) 0%, hsla(6, 77%, 85%, 1) 100%);
		background: -moz-linear-gradient(90deg, hsla(0, 87%, 79%, 1) 0%, hsla(6, 77%, 85%, 1) 100%);
		background: -webkit-linear-gradient(90deg, hsla(0, 87%, 79%, 1) 0%, hsla(6, 77%, 85%, 1) 100%);
		filter: progid: DXImageTransform.Microsoft.gradient( startColorstr="#F89999", endColorstr="#F6C0BA", GradientType=1 );
	}
	#lat{
		position:absolute;
		top: 0;
		left:50%;
		transform: translateX(-50%);
	}
	main {
		max-width:800px;
		width:300px;
		text-align: center;
		margin: 0;
		padding:1rem;
		margin: 1rem auto;
	}
	@media (min-width: 640px) {
		main {
			max-width: 90vw;
			width:400px;
		}
	}
</style>
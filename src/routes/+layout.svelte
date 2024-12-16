<script lang="ts">
	import '../app.css';
	import { loadSlim } from '@tsparticles/slim';
	import { MoveDirection, OutMode } from '@tsparticles/engine';
	import Particles, { particlesInit } from '@tsparticles/svelte';

	let particlesConfig = {
		background: {
			color: '#000'
		},
		particles: {
			number: {
				value: 500
			},
			move: {
				direction: MoveDirection.none,
				enable: true,
				outModes: {
					default: OutMode.out
				},
				random: true,
				speed: 0.1,
				straight: false
			},
			opacity: {
				animation: {
					enable: true,
					speed: 1,
					sync: false
				},
				value: { min: 0, max: 1 }
			},
			size: {
				value: { min: 1, max: 3 }
			}
		},
	};

	let onParticlesLoaded = (event: any) => {
		const particlesContainer = event.detail.particles;

		// you can use particlesContainer to call all the Container class
		// (from the core library) methods like play, pause, refresh, start, stop
	};

	void particlesInit(async (engine) => {
		// call this once per app
		// you can use main to customize the tsParticles instance adding presets or custom shapes
		// this loads the tsparticles package bundle, it's the easiest method for getting everything ready
		// starting from v2 you can add only the features you need reducing the bundle size
		//await loadFull(engine);
		await loadSlim(engine);
	});
</script>

<div class="h-screen overflow-hidden">
    <slot />
</div>

<Particles
    id="tsparticles"
    class="relative -z-10"
    options={particlesConfig}
    on:particlesLoaded={onParticlesLoaded}
/>
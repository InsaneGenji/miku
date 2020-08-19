<template>
	<div id="app">
		<Miku />
	</div>
</template>

<script>
	import Miku from './views/Miku.vue';

	export default {
		name: 'App',
		components: {
			Miku
		}
	}
</script>

<style lang="scss">
	body {
		background: url(./assets/bg-miku.jpg) no-repeat center center;
		background-size: cover;
		background-attachment: fixed;
	}

	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.icon {
		width: 1em;
		height: 1em;
		vertical-align: -0.15em;
		fill: currentColor;
		overflow: hidden;
	}
</style>

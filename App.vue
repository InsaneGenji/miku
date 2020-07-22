<script>
	export default {
		onLaunch() {
			console.log('App Launch');
		},
		onShow() {
			console.log('App Show');
		},
		onHide() {
			console.log('App Hide');
		}
	}
</script>

<style lang="scss">
	body {
		background: url(./static/bg-miku.jpg) no-repeat center center fixed;
		background-size: cover;
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

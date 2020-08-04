<template>
	<div class="container">
		<!-- LOGO -->
		<a href="https://zh.moegirl.org/初音未来#" class="logo"></a>

		<!-- 搜索栏 -->
		<form title="在网络上搜索" action="http://www.baidu.com/baidu">
			<input type="search" placeholder="在网络上搜索" name="word" autocomplete="off">
			<input type="submit" value="" title="搜索">
		</form>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				pageWidth: document.body.clientWidth
			};
		},
		mounted() {
			this.response();
		},
		methods: {
			response() {
				window.onresize = () => {
					if (document.body.clientWidth < 740) {
						console.log(document.body.clientWidth)
					}
				}
			}
		}
	}
</script>

<style scoped lang="scss">
	/* LOGO */
	.logo {
		width: 368px;
		height: 169px;
		background-image: url(../assets/logo-miku.png);
		background-size: cover;
		position: absolute;
		top: 89px;
		left: 0;
		right: 0;
		margin: 0 auto;
		transition: .39s;

		&:hover {
			transform: scale(1.05, 1.05);
		}
	}

	/* 搜索栏 */
	form {
		width: 777px;
		height: 50px;
		display: flex;
		align-items: center;
		position: absolute;
		top: 294px;
		left: 0;
		right: 0;
		margin: 0 auto;
		transition: .39s;

		input {
			&[type="search"] {
				width: 100%;
				height: 100%;
				font-size: 18px;
				color: rgba(255, 255, 255, 0.78);
				padding: 0 50px 0 57px;
				background: url(../assets/search-icon.png) no-repeat 9px center;
				background-size: 39px 39px;
				border-radius: 9px;
				border: 1px solid grey;

				&:focus {
					box-shadow: 0 0 39px rgba(0, 156, 155, 0.69);
				}
			}

			&[type="submit"] {
				width: 50px;
				height: 100%;
				background: url("../assets/search-button-link.png") no-repeat right center;
				background-size: 50px 100%;
				border: none;
				border-radius: 0 9px 9px 0;
				outline: none;
				cursor: pointer;
				position: absolute;
				right: 0;

				&:hover {
					background-image: url("../assets/search-button-hover.png");
				}

				&:active {
					background-image: url("../assets/search-button-active.png");
				}
			}
		}
	}
</style>

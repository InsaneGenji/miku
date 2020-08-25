<template>
	<div class="container">
		<!-- LOGO -->
		<a href="https://zh.moegirl.org/初音未来#" class="logo"></a>

		<!-- 搜索栏 -->
		<form title="在网络上搜索" action="http://www.baidu.com/s" :class="{focus: focusFlag }">
			<input type="search" placeholder="在网络上搜索" name="wd" @focus="inputFocus" @blur="inputBlur">
			<input type="submit" value="" title="搜索">
		</form>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				focusFlag: false
			};
		},
		mounted() {
			this.response();
		},
		methods: {
			inputFocus() {
				this.focusFlag = true;
			},
			inputBlur() {
				this.focusFlag = false;
			},
			response() {
				window.onresize = () => {
					if (document.body.clientWidth < 740) {
						console.log(document.body.clientWidth)
					}
				};
			}
		}
	}
</script>

<style lang="scss" scoped>
	/* LOGO */
	.logo {
		width: 368px;
		height: 169px;
		background-image: url(../assets/logo-miku.png);
		background-size: cover;
		margin: 89px 0 39px;
		transition: .39s;

		&:hover {
			transform: scale(1.05, 1.05);
		}
	}

	/* 搜索栏 */
	form {
		width: 777px;
		height: 50px;
		border: 1px solid grey;
		border-radius: 9px;
		display: flex;
		align-items: center;

		&.focus {
			box-shadow: 0 0 39px rgba(0, 156, 155, 0.69);
		}

		input {
			border: none;
			outline: none;
			display: flex;

			&[type="search"] {
				flex: 1;
				height: 100%;
				font-size: 18px;
				color: rgba(255, 255, 255, 0.78);
				padding: 0 50px 0 57px;
				background: url(../assets/search-icon.png) no-repeat 9px center;
				background-size: 39px 39px;
			}

			&[type="submit"] {
				width: 50px;
				height: 100%;
				background: url(../assets/arrow-right.png) no-repeat center center;
				background-size: 19px 19px;
				border-radius: 0 9px 9px 0;
				cursor: pointer;

				&:hover {
					background-color: rgba(150, 150, 150, .39);
				}

				&:active {
					background-color: rgba(200, 200, 200, .39);
				}
			}
		}
	}
</style>

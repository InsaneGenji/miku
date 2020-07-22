<template>
	<view class="container">
		<!-- LOGO -->
		<a href="https://zh.moegirl.org/初音未来#" class="logo"></a>

		<!-- 搜索栏 -->
		<form @submit="baidu" :class="{active:focusFlag}">
			<input placeholder="在网络上搜索" placeholder-style="color:rgba(233,233,233,.78);" maxlength="-1" @focus="focus" @blur="blur" />
			<button form-type="submit">
				<svg class="icon" aria-hidden="true">
					<use xlink:href="#icon-arrow-right"></use>
				</svg>
			</button>
		</form>
	</view>
</template>

<script>
	import('../../common/iconfont.js');

	export default {
		data() {
			return {
				focusFlag: false
			}
		},
		methods: {
			focus() {
				this.focusFlag = true;
			},
			blur() {
				this.focusFlag = false;
			},
			baidu() {
				console.log(1)
			}
		}
	}
</script>

<style lang="scss" scoped>
	/* LOGO */
	.logo {
		width: 184rpx;
		height: 84rpx;
		background-image: url(../../static/logo-miku.png);
		background-size: cover;
		margin: 45rpx 0 18rpx;
		transition: .39s;

		&:hover {
			transform: scale(1.05, 1.05);
		}
	}

	/* 搜索栏 */
	form {
		width: 369rpx;
		height: 25rpx;
		border: 1px solid #ccc;
		border-radius: 6rpx;
		overflow: hidden;
		position: relative;

		&.active {
			box-shadow: 0 0 18rpx rgba(0, 156, 155, 0.69);
		}

		input,
		button {
			height: 25rpx;
			position: absolute;
			top: 0;
		}

		input {
			width: 100%;
			font-size: 9rpx;
			color: rgba(255, 255, 255, 0.78);
			background: url(../../static/search-icon.png) no-repeat 5rpx center;
			background-size: 20rpx 20rpx;
			padding: 0 28rpx;
		}

		button {
			width: 25rpx;
			background-color: transparent;
			line-height: 25rpx;
			padding: 0;
			margin: 0;
			right: 0;

			&::after {
				border: 0;
				border-radius: 0;
			}
		}
	}
</style>

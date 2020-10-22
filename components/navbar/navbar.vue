<template>
	<view class="navbar">
		<view class="navbar-fixed">
			<view class="navbar-search">
				<view class="navbar-search-icon"></view>
				<view class="navbar-search-text">这里点击搜索</view>
			</view>
		</view>
		<view style="height: 45px;"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.navbar {
		.navbar-fixed {
			position: fixed;
			top: 0;
			left: 0;
			z-index: 999;
			display: flex;
			align-items: center;
			justify-content: center;
			padding: 0 15px;
			width: 100%;
			height: 45px;
			background-color: $base-color;
			box-sizing: border-box;
			.navbar-search {
				padding: 0 10px;
				display: flex;
				align-items: center;
				width: 100%;
				height: 30px;
				border-radius: 30px;
				background-color: #FFFFFF;
				.navbar-search-icon {
					width: 10px;
					height: 10px;
					background-color: red;
					margin-right: 10px;
				}
				.navbar-search-text {
					font-style: 12px;
					color: #999;
				}
			}
		}
	}
</style>

<template>
	<view class="navbar">
		<view class="navbar-fixed">
			<!-- 状态栏 -->
			<view :style="{height: statusBarHeight + 'px'}"></view>
			<!-- 导航栏 -->
			<view class="navbar-content" :style="{height:navBarHeight+'px',width:windowWidth+'px'}">
				<view class="navbar-search">
					<view class="navbar-search-icon">
						 <uni-icons type="search" size="16" color="#999"></uni-icons>
					</view>
					<view class="navbar-search-text">这里点击搜索</view>
				</view>
			</view>
		</view>
		<view :style="{height:statusBarHeight + navBarHeight +'px'}"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				statusBarHeight:20,
				navBarHeight:45,
				windowWidth: 375
			};
		},
		created() {
// 获取手机系统信息
			const info = uni.getSystemInfoSync()
			// 设置状态栏高度
			this.statusBarHeight = info.statusBarHeight
			this.windowWidth = info.windowWidth
			// h5 app mp-alipay
			// #ifndef H5 || APP-PLUS || MP-ALIPAY
			// 获取胶囊的位置
			const menuButtonInfo = uni.getMenuButtonBoundingClientRect()
			console.log(menuButtonInfo);
			// (胶囊底部高度 - 状态栏的高度) + (胶囊顶部高度 - 状态栏内的高度) = 导航栏的高度
			this.navBarHeight = (menuButtonInfo.bottom - info.statusBarHeight) + (menuButtonInfo.top - info.statusBarHeight)
			this.windowWidth = menuButtonInfo.left
			// #endif

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
			// display: flex;
			// align-items: center;
			// justify-content: center;
			// padding: 0 15px;
			width: 100%;
			// height: 45px;
			background-color: $base-color;
			// box-sizing: border-box;
			.navbar-content {
				padding: 0 15px;
				height: 45px;
				box-sizing: border-box;
				display: flex;
				align-items: center;
				justify-content: center;
				.navbar-search {
					padding: 0 10px;
					display: flex;
					align-items: center;
					width: 100%;
					height: 30px;
					border-radius: 30px;
					background-color: #FFFFFF;
					.navbar-search-icon {
						// width: 10px;
						// height: 10px;
						// background-color: red;
						margin-right: 10px;
					}
					.navbar-search-text {
						font-style: 12px;
						color: #999;
					}
				}
			}
		}
	}
</style>

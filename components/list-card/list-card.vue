<template>
	<view>
		<view class="list-card">
			<view class="list-card-img">
				<image src="/static/home-active.png" mode="aspectFill"></image>
			</view>
			<view class="list-card-content">
				<view class="list-card-content-title">
					<text>
						前端前端前端前端前端前端前端前端前端前端前端前端
						前端前端前端前端前端前端前端前端前端前端前端前端前端前端前端前端前端前端
				    </text>
				</view>
				<view class="list-card-content-des">
					<view class="list-card-content-des-label">
						<view class="list-card-content-des-label-item">前端</view>
					</view>
					<view class="list-card-content-des-browser">129浏览</view>
				</view>
			</view>
		</view>
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

<style lang="scss" scoped>
.list-card{
	display: flex;
	padding: 10px;
	margin: 10px;
	border-radius: 5px;
	box-shadow: 0 0 5px 1px #2C405A;
	box-sizing: border-box;
	.list-card-img{
		flex-shrink: 0;
		width: 60px;
		height: 60px;
		border-radius: 5px;
		overflow: hidden;
		image{
			width: 100%;
			height: 100%;
		}
	}
	.list-card-content{
		display: flex;
		flex-direction: column;
		padding-left: 10px;
		width: 100%;
		justify-content: space-between;
		.list-card-content-title {
			position: relative;
			padding-right: 30px;
			font-size: 14px;
			color: #333;
			font-weight: 400;
			line-height: 1.2;
			text {
				overflow: hidden;
				text-overflow: ellipsis;
				display: -webkit-box;
				-webkit-line-clamp: 2;
				-webkit-box-orient: vertical;
			}
			
		}
		.list-card-content-des {
			display: flex;
			justify-content: space-between;
			font-size: 12px;
			.list-card-content-des-label {
				display: flex;
				.list-card-content-des-label-item {
					padding: 0 5px;
					margin-right: 5px;
					border-radius: 15px;
					color: $base-color;
					border: 1px $base-color solid;
				}
			}
			.list-card-content-des-browser {
				color: #999;
				line-height: 1.5;
			}
		}
	}
}
</style>

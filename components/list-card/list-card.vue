<template>
	<view>
		<!-- 基础卡片 -->
		<view class="list-card" v-if="mode === 'base'">
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
		<!-- 多图模式 -->
		<view class="list-card mode-colomn" v-if="mode === 'middle'">
			<view class="list-card-content">
				<view class="list-card-content-title">
					<text>
						前端前端前端前端前端前端前端前端前端前端前端前端
						前端前端前端前端前端前端前端前端前端前端前端前端前端前端前端前端前端前端
				    </text>
				</view>
				<view class="list-card-img">
					<view v-for="item in 3" :key="item" class="list-card-image-item">
						<image src="/static/home-active.png" mode="aspectFill"></image>
					</view>
				</view>
				<view class="list-card-content-des">
					<view class="list-card-content-des-label">
						<view class="list-card-content-des-label-item">前端</view>
					</view>
					<view class="list-card-content-des-browser">129浏览</view>
				</view>
			</view>
		</view>
		<!-- 大图模式 -->
			<view class="list-card mode-bigimg" v-if="mode === 'big'">
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
		props:{
			mode:{
				type:String,
				default:"base"
			}
		},
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
	&.mode-colomn{
		.list-card-content{
			width: 100%;
			padding-left: 0;
		}
		.list-card-img{
			display: flex;
			margin-top: 10px;
			width: 100%;
			height: 70px;
			.list-card-image-item{
				margin-left: 10px;
				width: 100%;
				border-radius: 5px;
				overflow: hidden;
				&:first-child {
					margin-left: 0;
				}
				image{
					width: 100%;
					height: 100%;
				}
			}	
			}
			.list-card-content-des{
				margin-top: 10px;
		}
	}
	&.mode-bigimg{
		flex-direction: column;
		.list-card-img{
			width: 100%;
			height: 100px;
		}
		.list-card-content{
			padding-left: 0;
			margin-top: 10px;
		}
		.list-card-content-des{
			display: flex;
			align-items: center;
			margin-top: 10px;
		}
	}
}
</style>

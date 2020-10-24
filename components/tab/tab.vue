<template>
	<view class="tab ha">
		<scroll-view scroll-x class="tab-scroll">
			<view class="tab-scroll-box">
				<view class="tab-scroll-item" v-for="(item,index) in list" :key="item.id"
				@click="clicktab(item,index)" :class="{active:activeIndex === index}">{{item.name}}</view>
			</view>
		</scroll-view>
		<view class="tab-icon">
			<uni-icons type="gear" size="26" color="#666"></uni-icons>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			list:{
				type:Array
			}
		},
		methods:{
			clicktab(item,index) {
				this.activeIndex = index
				this.$emit('tabclick',{
					data:item,
					index
				})
			}
		},
		data() {
			return {
				activeIndex:0
			};
		}
	}
</script>

<style lang="scss">
	.tab {
		display: flex;
		width: 100%;
		box-sizing: border-box;
		background-color: #FFFFFF;
		border-bottom: 1px #f5f5f5 solid;
		.tab-scroll {
			flex: 1;
			overflow: hidden;
			box-sizing: border-box;
			.tab-scroll-box{
				display: flex;
				align-items: center;
				flex-wrap: nowrap;
				height: 45px;
				box-sizing: border-box;
				.tab-scroll-item {
					flex-shrink: 0;
					padding: 0 10px;
					color: #333;
					font-size: 14px;
					&.active{
						color: $base-color;
					}
				}
			}
		}
		.tab-icon {
			box-sizing: border-box;
			position: relative;
			display: flex;
			justify-content: center;
			align-items: center;
			width: 45px;
			&::after{
				content: '';
				position: absolute;
				top: 12px;
				bottom: 12px;
				left: 0;
				width: 1px;
				background-color: #ddd;
			}
		}
	}
</style>

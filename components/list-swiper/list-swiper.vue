<template>
	<view class="list-swiper-container">
		<swiper class="swiper" @change="change" :current="activeIndex">
			<swiper-item class="swiper-item" v-for="(item,index) in tab" :key="index">
				<list-swiper-item></list-swiper-item>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		props:{
			tab:{
				type:Array,
				default() {
					return []
				}
			},
			activeIndex:{
				type:Number,
				default:0
			}
		},
		watch:{
			activeIndex(newValue){
				this.activeIndex = newValue
			}
		},
		data() {
			return {
				
			};
		},
		methods:{
			change(e) {
				const {current} = e.detail
				console.log(current)
				this.$emit("change",current)
			}
		}
	}
</script>

<style lang="scss">
.list-swiper-container{
	height: 100%;
	.swiper{
		height: 100%!important;
	    .swiper-item{
		    height: 100%;
			overflow: hidden;
			.list-scroll{
				height: 100%;
			}
		}
}

}
</style>

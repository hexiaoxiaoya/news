<template>
	<view class="list-swiper-container">
		<swiper class="swiper">
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
			}
		},
		data() {
			return {
				
			};
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

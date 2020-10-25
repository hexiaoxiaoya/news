<template>
	<view class="home">
		<!-- 自定义组件：无需引入组件注意 -->
		<navbar></navbar>
		<tab :list="list" v-on:tabclick="tabclick" :tabindex="tabindex"></tab>
		<view class="home-list">
			<list-swiper :tab="list" @change="change" :activeIndex="activeIndex"></list-swiper>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				list: null,
				tabindex:0,
				activeIndex:0
			}
		},

		onLoad() {
			this.list = [{
					id: 1,
					name: "科技"
				},
				{
					id: 2,
					name: "金融"
				},
				{
					id: 3,
					name: "医疗"
				},
				{
					id: 4,
					name: "游戏"
				},
				{
					id: 5,
					name: "美容"
				},
				{
					id: 6,
					name: "资讯"
				},
				{
					id: 7,
					name: "时尚"
				},
				{
					id: 8,
					name: "游戏"
				},
				{
					id: 9,
					name: "留学"
				},
			]

		},
		methods: {
			tabclick({
				item,
				index
			}) {
				this.activeIndex = index
			},
			change(current) {
				this.tabindex = current
			}
		}
	}
</script>

<style lang="scss">
	page {
		height: 100%;
		display: flex;
	}

	.home {
		display: flex;
		flex-direction: column;
		flex: 1;
		overflow: hidden;

		.home-list {
			flex: 1;
			box-sizing: border-box;
		}
	}
</style>

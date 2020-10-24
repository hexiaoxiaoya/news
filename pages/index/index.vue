<template>
	<view class="content">
		<!-- 自定义组件：无需引入组件注意 -->
		<navbar></navbar>
		<tab :list="list" v-on:tabclick="tabclick"></tab>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				list:null
			}
		},
		
		onLoad() {
			this.list = [
					{id:1,name:"科技"},
					{id:2,name:"金融"},
					{id:3,name:"医疗"},
					{id:4,name:"游戏"},
					{id:5,name:"美容"},
					{id:6,name:"资讯"},
					{id:7,name:"时尚"},
					{id:8,name:"游戏"},
					{id:9,name:"留学"},
				]

		},
		methods: {
			tabclick({item,index}){
				console.log(index)
			}
		}
	}
</script>

<style lang="scss">
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>

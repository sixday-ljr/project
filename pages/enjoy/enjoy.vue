<template>
	<view class="enjoy">
		<!-- 顶部title -->
		<view class="enjoy_top">
			<image class="top_left" src="../../static/enjoy/enjoy_left.png" mode=""></image>
			<text class="top_center">享特惠</text>
			<text class="top_right" @click="collect()">我的收藏</text>
		</view>
		<!-- 全部分类 -->
		<view class="sort">
			<ren-dropdown-filter :filterData='filterData' :defaultIndex='defaultIndex' @ed='ed'
				@dateChange='dateChange'></ren-dropdown-filter>
		</view>
		<!-- 列表 -->
		<view class="list" v-for="list in lists" :key="list.id" @click="active()">
			<view class="list_top">
				<image class="list_left" :src="list.img" mode=""></image>
				<view class="list_right">
					<text>{{list.title}}</text>
					<text>{{list.time}}</text>
				</view>
			</view>
			<view class="list_bot">
				<text>{{list.location}}</text>
				<text>{{list.juli}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	import RenDropdownFilter from '@/components/ren-dropdown-filter/ren-dropdown-filter.vue'
	export default {
		components: {
			RenDropdownFilter
		},
		data() {
			return {
				filterData: [
					[{
							text: '全部分类',
							value: ''
						}, {
							text: '全部',
							value: 1
						}, {
							text: '运动健身',
							value: 2
						}, {
							text: '休闲旅游',
							value: 3
						},
						{
							text: '兴趣爱好',
							value: 3
						},
						{
							text: '保养',
							value: 3
						}, {	
							text: '团体活动',
							value: 3
						}, {
							text: '运动',
							value: 3
						},
						{
							text: '生活服务',
							value: 3
						}
					],
					[{
						text: '筛选',
						value: ''
					}, {
						text: '最新发布',
						value: 1
					}, {
						text: '离我最近',
						value: 2
					}, {
						text: '人气最旺',
						value: 3
					}]
				],
				defaultIndex: [0, 0],
				lists: [{
						img: 'https://dimg04.c-ctrip.com/images/200e0w000000kfwzgB29B_R_300_225_R5_Q70_D.jpg',
						title: '超实惠多人餐送包房',
						time: '2022-02-28至2022-03-08',
						location: '哈尔滨市香坊区公滨路572号',
						juli: '1.6km'
					},
					{
						img: 'https://dimg04.c-ctrip.com/images/200e0w000000kfwzgB29B_R_300_225_R5_Q70_D.jpg',
						title: '超实惠多人餐送包房',
						time: '2022-02-28至2022-03-08',
						location: '哈尔滨市香坊区公滨路572号',
						juli: '1.6km'
					},
					{
						img: 'https://dimg04.c-ctrip.com/images/200e0w000000kfwzgB29B_R_300_225_R5_Q70_D.jpg',
						title: '超实惠多人餐送包房',
						time: '2022-02-28至2022-03-08',
						location: '哈尔滨市香坊区公滨路572号',
						juli: '1.6km'
					},
					{
						img: 'https://dimg04.c-ctrip.com/images/200e0w000000kfwzgB29B_R_300_225_R5_Q70_D.jpg',
						title: '超实惠多人餐送包房',
						time: '2022-02-28至2022-03-08',
						location: '哈尔滨市香坊区公滨路572号',
						juli: '1.6km'
					},
					{
						img: 'https://dimg04.c-ctrip.com/images/200e0w000000kfwzgB29B_R_300_225_R5_Q70_D.jpg',
						title: '超实惠多人餐送包房',
						time: '2022-02-28至2022-03-08',
						location: '哈尔滨市香坊区公滨路572号',
						juli: '1.6km'
					}
				]
			}
		},

		onLoad() {

		},
		methods: {
			ed(res) {
				console.log(res)
			},
			dateChange(d) {
				uni.showToast({
					icon: 'none',
					title: d
				})
			},
			active() {
				uni.navigateTo({
					url: './activedetail'
				})
			},
			collect(){
				uni.navigateTo({
					url:'../mycollect/mycollect'
				})
			}
		}
	}
</script>

<style>
	.enjoy {
		background-color: #F0F1F1;
	}

	.enjoy_top {
		width: 100%;
		height: 72rpx;
		background: linear-gradient(to right, #FF3B26, #FF7105);

	}

	.top_center,
	.top_right {
		color: #FFFFFF;
		font-size: 50rpx;
		font-weight: bold;
		line-height: 72rpx;
	}

	.top_center {
		margin-left: 255rpx;
	}

	.top_right {
		font-size: 40rpx;
		margin-right: 26rpx;
		float: right;

	}

	.top_left {
		width: 21rpx;
		height: 37rpx;
		margin-left: 26rpx;
		padding-top: 20rpx;
		line-height: 72rpx;
		float: left;
	}

	.sort {
		height: 83rpx;
	}

	.list {
		width: 702rpx;
		height: 300rpx;
		background-color: #FFFFFF;
		margin: 22rpx 24rpx 20rpx 24rpx;
		border-radius: 20rpx;
	}

	.list_top {
		display: flex;
		justify-content: space-between;
	}

	.list_left {
		width: 160rpx;
		height: 160rpx;
		margin-top: 29rpx;
		margin-left: 33rpx;

	}

	.list_right>text {
		display: block;
	}

	.list_right>text:nth-child(1) {
		color: #333333;
		font-size: 50rpx;
		margin: 48rpx 38rpx 32rpx 0;
	}

	.list_right>text:nth-child(2) {

		color: #7A7A7A;
		font-size: 40rpx;

	}

	.list_bot {
		display: flex;
		justify-content: space-between;
		margin-top: 40rpx;
		padding: 0 34rpx;

	}

	.list_bot>text {
		font-size: 36rpx;
		color: #7A7A7A;
		display: block;
	}

	.list_bot>text:nth-child(1) {}
</style>

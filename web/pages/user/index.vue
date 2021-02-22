<template>
	<view>
		<view class="bg">
			<view class="user-info">
				<u-image width="70rpx" height="70rpx" shape="circle" :src="userInfo.avatar"></u-image>
				<view class="user-info__name u-line-1 u-p-l-12">{{ userInfo.name || '请登录' }}</view>
				<view class="user-info__more"><u-icon name="arrow-right" size="28"></u-icon></view>
			</view>
		</view>
		<view class="tool"></view>
		<view class="suspension-wrap">
			<view class="suspension">
				<view class="Sign u-flex suspension-item"><u-button type="primary" @click="$u.route('pages/user/sign/sign')" >签到</u-button></view>
				<view class="suspension-item u-flex-col">
					<view class="title u-type-info">50</view>
					<view class="title u-type-info">积分</view>
				</view>
				<view class="suspension-item u-flex-col">
					<view class="title u-type-info">1</view>
					<view class="title u-type-info">优惠券</view>
				</view>
			</view>
			
		</view>
		<view class="order-wrap">
			<u-cell-group :border="false"><u-cell-item :border-bottom="false" title="我的订单" value="更多"></u-cell-item></u-cell-group>
			<u-grid :col="5">
				<u-grid-item v-for="(item, index) in orderList" :key="index">
					<u-icon color="#9999AA" :name="item.icon" :size="46"></u-icon>
					<view class="u-m-t-24 u-tips-color">{{ item.title }}</view>
				</u-grid-item>
			</u-grid>
		</view>
		<view class="link-wrap">
			<u-cell-group><u-cell-item :title="item.title" v-for="(item, index) in links" :key="index" :arrow="item.isLink"></u-cell-item></u-cell-group>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			userInfo: {
				avatar: 'https://cdn.uviewui.com/uview/example/fade.jpg'
			},
			title: 'Hello',
			orderList: [
				{
					title: '全部订单',
					icon: 'order'
				},
				{
					title: '待付款',
					icon: 'calendar'
				},
				{
					title: '待发货',
					icon: 'gift'
				},
				{
					title: '待收货',
					icon: 'car'
				},
				{
					title: '退款/售后',
					icon: 'error-circle'
				}
			],
			links: [
				{
					title: '购物车',
					icon: 'hourglass',
					isLink: true,
					path: ''
				},
				{
					title: '地址管理',
					icon: 'hourglass',
					isLink: true,
					path: ''
				},
				{
					title: '在线客服',
					icon: 'hourglass',
					isLink: true,
					path: ''
				},
				{
					title: '退出登录',
					icon: 'hourglass',
					isLink: false,
					path: ''
				}
			]
		};
	},
	onLoad() {},
	methods: {}
};
</script>

<style lang="scss" scoped>
page {
	position: relative;
	.user-info {
		display: flex;
		color: white;
		.user-info__name {
			flex: 1;
			font-size: 34rpx;
			line-height: 70rpx;
		}
		.user-info__more {
			display: flex;
			align-items: center;
		}
		padding: 24rpx;
	}
	.bg {
		height: 300rpx;
		background-color: #464c5b;
	}
	.suspension-wrap {
		position: absolute;
		top: 225rpx;
		left: 48rpx;
		right: 48rpx;
		height: 150rpx;
		background-color: white;
		z-index: 10;
		padding: 24rpx 0;
		.suspension {
			display: flex;
			.suspension-item {
				&:nth-child(1),&:nth-child(2) {
					border-right: 2rpx solid #e4e7ed;
				}
				flex: 1;
				.title {
					line-height: 54rpx;
					text-align: center;
				}
			}
		}
		
	}
	.order-wrap {
		margin-top: 99rpx;
	}
	.link-wrap {
		margin: 24rpx 0;
	}
}
</style>

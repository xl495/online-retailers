<template>
	<view>
		<view class="bg">
			<view class="info-wrap">
				<view class="info u-flex-col">
					<view class="u-font-40">350</view>
					<view class="u-font-32">我的积分</view>
				</view>
				<view class="u-m-t-24"><u-button type="primary" size="medium">签到</u-button></view>
			</view>
		</view>
		<view class="num-wrap">
			<view class="num-item">
				<view class="num-item__num">15次</view>
				<view class="num-item__title">总计签到</view>
			</view>
			<view class="num-item">
				<view class="num-item__num">15</view>
				<view class="num-item__title">签到积分</view>
			</view>
		</view>
		<view class="sign-wrap">
			<view class="sign-list">
				<u-grid :col="7" :border="false" >
					<u-grid-item v-for="(item, index) in list" :key="index">
						<u-icon :name="item.isSign ? 'star-fill' : 'star'" :size="46"></u-icon>
						<view class="grid-text">{{ item.time }}</view>
					</u-grid-item>
				</u-grid>
			</view>
		</view>
		<view class="sign-info">
			<u-divider color="#000000" :font-size="32">签到规则</u-divider>
			<view class="sign-info-rule u-m-t-24">
				<view class="sign-info-rule-item" v-for="(item, index) in rule" :key="index">
					<text class="u-font-48">●</text>
					<text class="u-p-l-12">{{ item }}</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			list: [
				{
					isSign: false,
					time: '11.22'
				},
				{
					isSign: false,
					time: '11.23'
				},
				{
					isSign: false,
					time: '11.24'
				},
				{
					isSign: false,
					time: '11.25'
				},
				{
					isSign: true,
					time: '11.26'
				},
				{
					isSign: false,
					time: '11.27'
				},
				{
					isSign: false,
					time: '11.27'
				}
			],
			rule: [
				'每天只能签到一次',
				'客户获得签到积分奖励，自领取之日起一年有效期。',
				'积分最终解释权归国瑞商业购物中心所有。'
			]
		};
	},
	methods: {}
};
</script>

<style lang="scss" scoped>
page {
	.bg {
		position: relative;
		width: 100%;
		height: 500rpx;
		background-color: #999999;
	}
	.info-wrap {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 500rpx;
		.info {
			display: flex;
			justify-content: center;
			align-items: center;
			color: white;
			width: 200rpx;
			height: 200rpx;
			border-radius: 50%;
			border: 2rpx solid white;
		}
	}
	.num-wrap {
		background-color: #000000;
		display: flex;
		height: 130rpx;
		.num-item {
			flex: 1;
			text-align: center;
			color: white;
			line-height: 65rpx;
			.num-item__num {
				font-weight: 600;
			}
			.num-item__title {
			}
		}
	}
	.sign-info {
		padding: 48rpx 24rpx;
		background-color: white;
		.sign-info-rule-item {
			font-size: 28rpx;
			font-weight: 500;
			line-height: 48rpx;
		}
	}
}
</style>

<template>
	<view class="content" :class="!headerInfo.isflag ? 'u-f-r-c' : 'u-f-c-c-c'">
		<!-- 左右布局 -->
		<template v-if="!headerInfo.isflag">
			<view class="info-pic"><image :src="headerInfo.img" lazy-load :style="imgW_H"></image></view>
			<view class="u-f-1 u-h-e-n info-content">
				<view class="title">{{ headerInfo.delivery_time }} | {{ headerInfo.distance }}</view>
				<view class="text u-h-e-n">公告：{{ headerInfo.announcement }}</view>
			</view>
		</template>
		<template v-else>
			<view class="info-pic"><image :src="headerInfo.img" lazy-load :style="imgW_H"></image></view>
			<view class="storeName">
				{{ headerInfo.storeName }}
				<text class="icon iconfont" :class="headerInfo.icon"></text>
			</view>
			<view class="u-f-r-c attention-info">
				<view class="attention">评价{{ headerInfo.attention }}</view>
				<view class="sales">月售{{ headerInfo.sales }}单</view>
				<view class="delivery-time">配送时间{{ headerInfo.delivery_time }}</view>
			</view>
			<view class="coupon-info u-f-r-c-a" style="width: 100%;">
				<view class="u-f-r-c">
					<block v-for="(item, index) in coupon" :key="index"><coupon-list :item="item"></coupon-list></block>
				</view>
				<view class="u-f-r-c">
					{{ coupon.length }}个优惠
					<text class=" icon iconfont icon-biaotou-daoxu" style="font-size: 25upx;"></text>
				</view>
			</view>
			<view style="width: 100%;" class="announcement">
				<view class="text u-h-e-n">公告：{{ headerInfo.announcement }}</view>
			</view>
		</template>
	</view>
</template>

<script>
import couponList from '../coupon-list/coupon-list.vue';
export default {
	components: {
		couponList
	},
	props: {
		imgW_H: {
			type: String,
			default: ''
		},
		headerInfo: Object
	},
	data() {
		return {
			// 优惠卷
			coupon: ['18减2', '35减5', '50减10', '配送费优惠']
		};
	}
};
</script>

<style scoped>
.content {
	background: #2e2f3b;
	padding: 10upx 20upx;
	color: #fff;
}

.info-pic > image {
	width: 100%;
	flex-shrink: 0;
}

.info-content {
	padding: 0upx 20upx;
}
.info-content .title {
	font-size: 24upx;
}
.info-content .text {
	font-size: 20upx;
}
.attention-info > view:nth-child(2) {
	margin: 0 20upx;
}

.storeName {
	font-size: 36upx;
}
.storeName > text {
	font-size: 36upx;
}
.attention-info > view,
.announcement > .text,
.coupon-info > view {
	font-size: 20upx;
}
</style>

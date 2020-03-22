<template>
	<view class="swiper-item u-f-r">
		<image :src="item.img" lazy-load></image>
		<view class="u-f-1">
			<view class="title">{{ item.title }}</view>
			<view class="content">{{ item.content }}</view>
			<view class="xs-info u-f-r-c">
				<view class="xs">月售{{ item.xs }}</view>
				<view class="dianzan">赞{{ item.dianzan }}</view>
			</view>
			<view class="shop u-f-r-c-b">
				<view class="pirce">
					￥{{ item.pirce }}/
					<text class="qibu">{{ item.qibu }}</text>
				</view>
				<view v-if="item.isflag" class="guige">选择格</view>
				<view v-if="!item.isflag" class="jiahao u-f-c-c-c">+</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	props: {
		item: Object,
		index: Number
	}
};
</script>

<style scoped>
.swiper-item {
	margin: 20upx 0;
	align-items: flex-start;
}
.swiper-item image {
	width: 120upx;
	height: 120upx;
	flex-shrink: 0;
	margin: 0 20upx;
}

.title {
	font-size: 30upx;
	font-weight: bold;
	color: #333333;
	margin-top: -15upx;
}
.content {
	font-size: 22upx;
	color: #666666;
}

.pirce {
	color: #fb4e44;
	font-size: 23upx;
	font-weight: bold;
}

.qibu {
	font-size: 20upx;
	color: #999;
	font-weight: 100;
}
.xs-info > view {
	font-size: 22upx;
	color: #666;
	margin: 0 10upx 0 0;
}
.jiahao {
	width: 40upx;
	height: 40upx;
	border-radius: 50%;
	background: #ffbd27;
	margin-right: 20upx;
	font-size: 30upx;
	font-weight: bold;
}
.guige {
	font-size: 20upx;
	padding: 5upx 20upx;
	background: #ffbd27;
	border-radius: 20upx;
	margin-right: 20upx;
	
}
</style>

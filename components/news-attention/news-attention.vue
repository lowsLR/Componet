<template>
	<view class="u-f-r-c content">
		<view v-if="item.biaozhi" class="biaozhi">{{ item.biaozhi }}</view>
		<view class="laiyuan">{{ item.laiyuan }}</view>
		<view class="attention">评论{{ item.attention }}</view>
		<view class="tiem" v-if="item.time">{{ item.time }}</view>
	</view>
</template>

<script>
export default {
	props: {
		item: Object
	}
};
</script>

<style scoped>
.content > view {
	font-size: 18upx;
	margin-right: 20upx;
	color: #999;
}
.biaozhi {
	border: 1px solid rgba(248, 89, 89, 0.5);
	color: #f85959 !important;
	width: 20upx;
	height: 20upx;
	font-size: 8upx !important;
	text-align: center;
	line-height: 20upx;
}
</style>

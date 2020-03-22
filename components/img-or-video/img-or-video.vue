<template>
	<view class="container">
		<block v-for="(item, index) in imgOrVideo" :key="index">
			<view style="padding: 20upx 0;">
				<view class="title">{{ item.title }}</view>
				<view class="imgorvideo u-f-c-c-c">
					<image :src="item.img" :style="imgW_h" v-if="item.img"></image>
					<view class="play icon iconfont icon-bofang" v-if="item.play"></view>
				</view>
				<view class="content">{{ item.content }}</view>
			</view>
			<!-- 线条line-border -->
			<line-border lineBorder="border:1upx solid #eee;margin-top:20upx"></line-border>
		</block>
	</view>
</template>

<script>
// 线条line-border
import lineBorder from '../line-border/line-border.vue';
export default {
	components: {
		lineBorder
	},
	props: {
		imgW_h: {
			type: String,
			default: ''
		},
		imgOrVideo: Array
	},
	data() {
		return {};
	}
};
</script>

<style scoped>
.container {
	padding: 20upx;
}
.title {
	font-size: 36upx;
}
.imgorvideo {
	position: relative;
}
.imgorvideo > image {
	width: 100%;
	display: block;
	margin: 10upx 0;
}
.play {
	font-size: 80upx;
	position: absolute;
	z-index: 10;
	color: #333;
}
.content {
	font-size: 30upx;
}
</style>

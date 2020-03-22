<template>
	<view style="padding: 20upx;">
		<block v-for="(item, index) in newsFlex" :key="index">
			
			<!-- 只有标题 -->
			<template v-if="item.imgarr.length == 0">
				<view style="padding: 10upx 0;">
					<view class="title">{{ item.title }}</view>
				</view>
			</template>
			
			<!-- 多张图片 -->
			<template v-if="item.imgarr.length > 1">
				<view style="padding: 10upx 0;">
					<view class="title">{{ item.title }}</view>
					<view class="u-f-r-c img">
						<block v-for="(t, i) in item.imgarr" :key="i"><image :src="t.img" :style="imgArrW_h"></image></block>
					</view>
				</view>
			</template>
			
			<!-- 单张图片 -->
			<template v-if="item.imgarr.length == 1">
				<view class="u-f-r-c" style="padding: 15upx 0;">
					<view>
						<view class="title">{{ item.title }}</view>

						<!-- 评论信息 -->
						<news-attention :item="item"></news-attention>
					</view>
					<view>
						<block v-for="(t, i) in item.imgarr" :key="i"><image :src="t.img" :style="imgW_h"></image></block>
					</view>
				</view>
			</template>
			
			<!-- 评论信息 -->
			<news-attention :item="item" v-if="item.imgarr.length !== 1"></news-attention>
			
			<!-- 线条line-border -->
			<line-border lineBorder="border:1upx solid #eee;margin-top:20upx"></line-border>
		</block>
	</view>
</template>

<script>
// 线条line-border
import lineBorder from '../line-border/line-border.vue';
// 评论信息
import newsAttention from '../news-attention/news-attention.vue';
export default {
	components: {
		lineBorder,
		newsAttention
	},
	props:{
		newsFlex:Array,
		// 上下布局的图片大小
		imgArrW_h:{
			type:String,
			default:''
		},
		// 左右布局的图片大小
		imgW_h:{
			type:String,
			default:''
		},
	}
};
</script>

<style scoped>
.title {
	font-size: 32upx;
}
.img > image:last-child {
	margin-right: 0 !important;
}
</style>

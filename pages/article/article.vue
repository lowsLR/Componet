<template>
	<view style="margin-bottom: 50px;">
		<!-- 自定义的顶部样式uni-nav-bar -->
		<uni-nav-bar :shadow="false" :border="false" backgroundColor="#d43d3d" color="#fff">
			<!-- 左边图标 -->
			<block slot="left"><view class="icon iconfont icon-xin-xianxing" style="font-size: 25px;margin-left: 40upx;"></view></block>
			<!-- 中间搜索框 -->
			<view style="display: flex;align-items: center;justify-content: center;font-size: 33upx;height: 100%; font-weight: bold;">
				今日头条
				<view class="icon iconfont icon-shuaxin" style="margin-left:5upx;font-weight: 100;"></view>
			</view>
			<!-- 右边图标 -->
			<block slot="right"><view class="icon iconfont icon-sousuo-xianxing" style="font-size: 25px;"></view></block>
		</uni-nav-bar>

		<!-- tar选项卡 -->
		<swiper-tab
			:tabBars="tabBars"
			:tabIndex="tabIndex"
			@changeTab="changeTab"
			scrollH="height:80upx"
			scrollBorderBottom="border:none;background:#f4f5f6;height:80upx;line-height:80upx;"
			scrollB_b="border:none;"
			:msk="true"
			mskStyle="width:80upx;height:80upx;background:#f4f5f6;color:#d43d3d;font-size:40upx"
		></swiper-tab>

		<!-- news-flex布局 -->
		<news-flex 
		:newsFlex="newsFlex" 
		imgArrW_h="flex:1;height:200upx;margin-right:6upx" 
		imgW_h="width:250upx;height:180upx">
		</news-flex>
		
		<!-- 图片or视频类型 imgOrVideo-->
		<img-or-video imgW_h="height:360upx;" :imgOrVideo="imgOrVideo"></img-or-video>
	</view>
</template>

<script>
// 自定义的顶部样式
import uniNavBar from '../../components/uni-nav-bar/uni-nav-bar.vue';
// 选项卡
import swiperTab from '../../components/swiper-tab/swiper-tab.vue';
// news-flex布局
import newsFlex from '../../components/news-flex/news-flex.vue';
// 图片or视频类型 imgOrVideo
import imgOrVideo from '../../components/img-or-video/img-or-video.vue';
export default {
	components: {
		uniNavBar,
		swiperTab,
		newsFlex,
		imgOrVideo
	},
	data() {
		return {
			// 选项卡
			tabIndex: 0,
			tabBars: [
				{
					name: '推荐1',
					id: 'tuijian1'
				},
				{
					name: '推荐2',
					id: 'tuijian2'
				},
				{
					name: '推荐3',
					id: 'tuijian3'
				},
				{
					name: '推荐4',
					id: 'tuijian4'
				},
				{
					name: '推荐5',
					id: 'tuijian5'
				},
				{
					name: '推荐6',
					id: 'tuijian6'
				},
				{
					name: '推荐7',
					id: 'tuijian7'
				},
				{
					name: '',
					id: 'tuijian8'
				}
			],
			// news-flex布局
			newsFlex: [
				{
					title: '除了中国，试问全球哪国能做到？钟南山院士发最强音，引爆舆论',
					biaozhi: '热',
					laiyuan: '英国报社1',
					attention: '22',
					time: '一个小时前',
					imgarr: [
						{
							img: '../../static/newsFlex/newsFlex1.jpg'
						},
						{
							img: '../../static/newsFlex/newsFlex1.jpg'
						},
						{
							img: '../../static/newsFlex/newsFlex1.jpg'
						}
					]
				},
				{
					title: '除了中国，试问全球哪国能做到？钟南山院士发最强音，引爆舆论',
					biaozhi: '热',
					laiyuan: '英国报社1',
					attention: '222',
					time: '2020-03-10',
					imgarr: []
				},
				{
					title: '最高调的点赞！中国抗疫被污名化，世界卫生界“老大哥”一句话堵住所有人的嘴',
					biaozhi: '热',
					laiyuan: '英国报社1',
					attention: '22',
					time: '一个小时前',
					imgarr: [
						{
							img: '../../static/newsFlex/newsFlex2.jpg'
						}
					]
				},
				{
					title: '最高调的点赞！中国抗疫被污名化，世界卫生界“老大哥”一句话堵住所有人的嘴',
					biaozhi: '',
					laiyuan: '英国报社1',
					attention: '22',
					time: '一个小时前',
					imgarr: [
						{
							img: '../../static/newsFlex/newsFlex2.jpg'
						}
					]
				},
				{
					title: '最高调的点赞！中国抗疫被污名化，世界卫生界“老大哥”一句话堵住所有人的嘴',
					biaozhi: '',
					laiyuan: '英国报社1',
					attention: '0',
					time: '',
					imgarr: [
						{
							img: '../../static/newsFlex/newsFlex2.jpg'
						}
					]
				}
			],
			// 图片or视频类型 imgOrVideo
			imgOrVideo: [
				{
					title: '苹果手机里有多少隐藏小功能？',
					img: '',
					play: false,
					content: '我是苹果小白，我第一次看到里面很多功能我适用，对我肯定就是隐藏的功能啊。…'
				},
				{
					title: '苹果手机里有多少隐藏小功能？',
					img: '../../static/imgOrVideo/imgOrVideo1.jpg',
					play: false,
					content: '我是苹果小白，我第一次看到里面很多功能我适用，对我肯定就是隐藏的功能啊。…'
				},
				{
					title: '苹果手机里有多少隐藏小功能？',
					img: '../../static/imgOrVideo/imgOrVideo1.jpg',
					play: true,
					content: '我是苹果小白，我第一次看到里面很多功能我适用，对我肯定就是隐藏的功能啊。…'
				}
			]
		};
	},
	methods: {
		// 选项卡
		changeTab(index) {
			this.tabIndex = index;
		}
	}
};
</script>

<style></style>

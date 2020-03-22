<template>
	<view style="margin-bottom: 50px;">
		<!-- 自定义的顶部样式uni-nav-bar -->
		<uni-nav-bar :shadow="false" :border="false" backgroundColor="#f2f2f2">
			<!-- 左边图标 -->
			<block slot="left"><view class="icon iconfont icon-shangyiyehoutuifanhui" style="font-size: 25px;margin-left: 20upx;"></view></block>
			<!-- 中间搜索框 -->
			<view style="display: flex;align-items: center;border-radius: 4px;margin-left: -46upx;height: 60upx;margin-top: 12upx;color: #CCCCCC;background: #FFFFFF;">
				<view class="icon iconfont icon-sousuo-xianxing" style="margin:0 20upx;"></view>
				搜索商品名称
			</view>
			<!-- 右边图标 -->
			<block slot="right"><view class="icon iconfont icon-yonghu-xianxing" style="font-size: 25px;"></view></block>
		</uni-nav-bar>

		<!-- tar选项卡 -->
		<swiper-tab :tabBars="tabBars" :tabIndex="tabIndex" @changeTab="changeTab" scrollBorderBottom="background:#f2f2f2;"></swiper-tab>

		<!-- 轮播图banner -->
		<banner :banner="banner"></banner>

		<!-- iconItem选项 -->
		<icon-item iconWidth="width:20%" :iconItem="iconItem"></icon-item>

		<!-- 线条line-border -->
		<line-border lineBorder="border:8upx solid #f0f0f0"></line-border>

		<!-- 图片流式布局LiquidLayout-多张 -->
		<liquid-layout :liquidLayout="liquidLayoutMove" imgHeight="height: 600upx"></liquid-layout>

		<!-- 线条line-border -->
		<line-border lineBorder="border:8upx solid #f0f0f0"></line-border>

		<!-- 图片流式布局LiquidLayout-单张 -->
		<liquid-layout :liquidLayout="liquidLayoutOne" imgHeight="height: 300upx"></liquid-layout>

		<!-- 线条line-border -->
		<line-border lineBorder="border:8upx solid #f0f0f0"></line-border>

		<!-- flex左右布局felxLr -->
		<flex-lr
			padding="padding: 20upx"
			width="width:49%"
			imgH_bR="height:280upx;border-radius:15upx"
			infoW_H_bR="width:50upx;height:50upx;border-radius:50%"
			:flexLr="flexLr"
		></flex-lr>

		<!-- 更多 -->
		<load-more title="加载更多" icon="icon-xiayiyeqianjinchakangengduo"></load-more>
	</view>
</template>

<script>
// 自定义的顶部样式
import uniNavBar from '../../components/uni-nav-bar/uni-nav-bar.vue';
// 选项卡
import swiperTab from '../../components/swiper-tab/swiper-tab.vue';
// 轮播图
import banner from '../../components/banner/banner.vue';
// iconItem选项
import iconItem from '../../components/icon-item/icon-item.vue';
// 线条
import lineBorder from '../../components/line-border/line-border';
// 图片流式布局
import liquidLayout from '../../components/liquid-layout/liquid-layout';
// flex左右布局
import flexLr from '../../components/flex-lr/flex-lr';
// 更多
import loadMore from '../../components/load-more/load-more';
export default {
	components: {
		uniNavBar,
		swiperTab,
		banner,
		iconItem,
		lineBorder,
		liquidLayout,
		flexLr,
		loadMore
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
				}
			],
			// 轮播图
			banner: [
				{
					img: '../../static/banner/banner1.jpg',
					id: 0
				},
				{
					img: '../../static/banner/banner2.jpg',
					id: 1
				}
			],
			// iconItem选项
			iconItem: [
				// {
				// 	type: 'wz',
				// 	content: 'icon-qiyeyuanquwuye',
				// 	text: '小米秒杀'
				// },
				// {
				// 	type: 'tp',
				// 	content: '../../static/iconItem/iconItem1.png',
				// 	text: '小米秒杀'
				// },
				{
					type: 'tp',
					content: '../../static/iconItem/iconItem1.png',
					text: ''
				},
				{
					type: 'tp',
					content: '../../static/iconItem/iconItem1.png',
					text: ''
				},
				{
					type: 'tp',
					content: '../../static/iconItem/iconItem1.png',
					text: ''
				},
				{
					type: 'tp',
					content: '../../static/iconItem/iconItem1.png',
					text: ''
				},
				{
					type: 'tp',
					content: '../../static/iconItem/iconItem1.png',
					text: ''
				},
				{
					type: 'tp',
					content: '../../static/iconItem/iconItem1.png',
					text: ''
				},
				{
					type: 'tp',
					content: '../../static/iconItem/iconItem1.png',
					text: ''
				},
				{
					type: 'tp',
					content: '../../static/iconItem/iconItem1.png',
					text: ''
				},
				{
					type: 'tp',
					content: '../../static/iconItem/iconItem1.png',
					text: ''
				},
				{
					type: 'tp',
					content: '../../static/iconItem/iconItem1.png',
					text: ''
				}
			],
			// 图片流式布局
			liquidLayoutMove: {
				type: 'layout', // all-单张图片，layout-两张以上
				img: [
					{
						imgpic: '../../static/LiquidLayout/LiquidLayout1.jpg',
						type: 'entireImg'
					},
					{
						imgpic: '../../static/banner/banner1.jpg',
						type: 'topImg'
					},
					{
						imgpic: '../../static/LiquidLayout/LiquidLayout1.jpg',
						type: 'bottomImg'
					}
				]
			},
			liquidLayoutOne: {
				type: 'all', // all-单张图片，layout-两张以上
				img: [
					{
						imgpic: '../../static/LiquidLayout/LiquidLayout2.jpg',
						type: 'allImg'
					}
				]
			},
			// flex左右布局
			flexLr: [
				{
					img: '../../static/flexLr/flexLr1.jpg',
					content: { isflag: true, title: '标题', text: '内容', price: '价格', isShop: true }
				},
				{
					img: '../../static/flexLr/flexLr1.jpg',
					content: { isflag: true, title: '标题', text: '', price: '', isShop: false }
				},
				{
					img: '../../static/flexLr/flexLr1.jpg',
					content: {
						isflag: false,
						title: '#标题',
						text: '内容...',
						price: '',
						isShop: false,
						info: [
							{
								infopic: '../../static/flexLr/info/info1.jpg',
								title: '米兔',
								icon: 'icon-xianshikejian',
								num: '2566'
							}
						]
					}
				}
			]
		};
	},
	onLoad() {},
	methods: {
		// 选项卡
		changeTab(index) {
			this.tabIndex = index;
		}
	}
};
</script>

<style></style>

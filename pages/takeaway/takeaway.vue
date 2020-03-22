<template>
	<view style="margin-bottom: 50px;">
		<!-- 自定义的顶部样式uni-nav-bar -->
		<uni-nav-bar :shadow="false" :border="false" backgroundColor="#2E2F3B" color="#fff">
			<!-- 左边图标 -->
			<block slot="left"><view class="icon iconfont icon-shangyiyehoutuifanhui" style="font-size: 25px;margin-left: 20upx;"></view></block>
		</uni-nav-bar>

		<!-- 线条line-border -->
		<line-border lineBorder="border-top:1upx solid #fff"></line-border>

		<!-- 头部信息 -->
		<header-info imgW_H="width:160upx;height:160upx" :headerInfo="headerInfo"></header-info>

		<!-- tar选项卡 -->
		<swiper-tab :tabBars="tabBars" :tabIndex="tabIndex" @changeTab="changeTab" scrollWidth="width:33.3%;font-size:28upx;font-weight:100"></swiper-tab>

		<!-- 点餐栏 -->
		<order-column></order-column>
	</view>
</template>

<script>
// 自定义的顶部样式
import uniNavBar from '../../components/uni-nav-bar/uni-nav-bar.vue';
// 线条
import lineBorder from '../../components/line-border/line-border';
// 头部信息
import headerInfo from '../../components/header-info/header-info';
// 选项卡
import swiperTab from '../../components/swiper-tab/swiper-tab.vue';
// 选项卡
import orderColumn from '../../components/order-column/order-column.vue';
export default {
	components: {
		uniNavBar,
		lineBorder,
		headerInfo,
		swiperTab,
		orderColumn
	},
	data() {
		return {
			// 选项卡
			tabIndex: 0,
			tabBars: [
				{
					name: '点菜',
					id: 'diancai'
				},
				{
					name: '评价',
					id: 'pingjia'
				},
				{
					name: '商家',
					id: 'shangjia'
				}
			],
			// 头部信息
			headerInfo: {
				isflag: false, //false--左右布局，true居中布局
				img: '../../static/headerInfo/headerInfo1.jpg',
				delivery_time: '60分钟',
				distance: '19.4km',
				announcement: '欢迎大家光临本店，本店一直秉持着用好的食材和用心的态度给顾客带来好的用餐体验！如有问题，请及时联系我们。电话：18826075908',
				attention: '4.9',
				sales: 369,
				storeName: '正宗柳州螺蛳粉',
				icon: 'icon-xiayiyeqianjinchakangengduo'
			}
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

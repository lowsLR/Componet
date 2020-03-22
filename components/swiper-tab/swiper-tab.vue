<template>
	<view class="uni-tab-bar" :style="scrollH">
		<scroll-view scroll-x class="uni-swiper-tab" :style="scrollBorderBottom">
			<block v-for="(tab, index) in tabBars" :key="tab.id">
				<view class="swiper-tab-list" :class="{ active: tabIndex == index }" @click="tabtap(index)" :style="scrollWidth">
					{{ tab.name }}
					<view class="swiper-tab-line" :style="scrollB_b"></view>
				</view>
			</block>
		</scroll-view>
		<!-- 遮挡框 -->
		<view class="msk u-f-c-c-c icon iconfont icon-jia" v-if="msk" :style="mskStyle"></view>
	</view>
</template>

<script>
export default {
	props: {
		tabBars: Array,
		tabIndex: Number,
		scrollBorderBottom: {
			type: String,
			default: ''
		},
		//主要字体间距和大小
		scrollWidth: {
			type: String,
			default: ''
		},
		//下划线
		scrollB_b: {
			type: String,
			default: ''
		},
		//主要调高度
		scrollH: {
			type: String,
			default: ''
		},
		// 遮挡框是否显示
		msk: {
			type: Boolean,
			default: false
		},
		// 遮挡框的样式
		mskStyle: {
			type: String,
			default: ''
		}
	},
	methods: {
		tabtap(index) {
			this.$emit('changeTab', index);
		}
	}
};
</script>

<style scoped>
.uni-swiper-tab {
	/* 选项卡的下划线 */
	border-bottom: 1upx solid #eeeeee;
}
.swiper-tab-list {
	color: #969696;
	font-weight: bold;
}
.uni-tab-bar .active {
	color: #f76260;
}
/*下滑线 */
.active .swiper-tab-line {
	border-bottom: 3upx solid #f76260;
	width: 70upx;
	margin: 20upx auto;
	border-top: 3upx solid #f76260;
	border-radius: 20upx;
}

.msk {
	position: absolute;
	right: 0;
	z-index: 10;
	border-right: 1upx solid rgba(244, 245, 246, 0.3);
}
</style>

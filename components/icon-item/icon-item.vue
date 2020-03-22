<template>
	<view class="container u-f-r-c u-f-w">
		<block v-for="(item, index) in iconItem" :key="index">
			<view class="u-f-c-c-c" :style="iconWidth">
				<template v-if="item.type == 'tp'">
					<image :src="item.content" lazy-load></image>
					<view v-if="item.text.length > 1">{{ item.text }}</view>
				</template>
				<template v-else>
					<view class="icon iconfont wenzi" :class="item.content"></view>
					<view>{{ item.text }}</view>
				</template>
			</view>
		</block>
	</view>
</template>

<script>
export default {
	props: {
		// 间距
		iconWidth: {
			type: String,
			default: 'width:20%'
		},
		iconItem: Array
	}
};
</script>

<style scoped>
.container {
	padding: 20upx;
}

.container > view {
	box-sizing: border-box;
}
/* 文字大小 -字体颜色*/
.container > view > view:last-child {
	font-size: 25upx;
	color: #6d6d72;
}
.wenzi {
	font-size: 50upx;
	color: #007aff;
}

/* 图片大小 */
.container image {
	width: 120upx;
	height: 120upx;
	border-radius: 50%;
	margin: 10upx 0;
}
</style>

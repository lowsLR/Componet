<template>
	<view class="u-f-r-c-c content">
		<view class="title">
			{{ title }}
			<text class="icon iconfont" :class="icon"></text>
		</view>
	</view>
</template>

<script>
export default {
	props: {
		title: String,
		icon: {
			type: String,
			default: ''
		}
	}
};
</script>

<style scoped>
.content {
	padding: 10upx 0;
	background: #EEEEEE;
}
.title {
	font-size: 32upx;
}
</style>

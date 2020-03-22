<template>
	<view>{{ item }}</view>
</template>

<script>
export default {
	props: {
		item: String
	},
	data() {
		return {};
	}
};
</script>

<style scoped>
	view{
		height: 30upx;
		padding: 0 6upx;
		border: 1upx solid #f76260;
		border-radius: 4upx;
		box-sizing: border-box;
		color: #f76260;
		margin-right: 20upx;
		font-size: 16upx;
	}
</style>

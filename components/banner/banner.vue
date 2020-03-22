<template>
	<view>
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item v-for="(item, index) in banner" :key="index"><image :src="item.img" lazy-load></image></swiper-item>
		</swiper>
	</view>
</template>

<script>
export default {
	props: {
		banner: Array
	}
};
</script>

<style scoped>
/* 图片的大小 */
swiper {
	height: 400upx;
}
image {
	width: 100%;
}
</style>

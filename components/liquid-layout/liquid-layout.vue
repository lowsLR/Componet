<template>
	<view class="u-f-r-c" :style="(imgHeight, flexDirection)">
		<template v-if="liquidLayout.type == 'layout'">
			<view class="left u-f-1" :class="flexDirection ? 'marginLeft' : 'marginRight'"><image :src="entireImg" lazy-load :style="imgHeight"></image></view>

			<view class="right u-f-1 u-f-c-c-c" :style="imgHeight">
				<image v-if="topImg" :src="topImg" lazy-load></image>
				<image v-if="bottomImg" :src="bottomImg" lazy-load></image>
			</view>
		</template>
		<template v-if="liquidLayout.type == 'all'">
			<image :src="allImg" lazy-load :style="imgHeight"></image>
		</template>
	</view>
</template>

<script>
export default {
	props: {
		liquidLayout: Object,
		// 图片高度
		imgHeight: {
			type: String,
			default: ''
		},
		//左右布局相反
		flexDirection: {
			type: String,
			default: ''
			// default:'flex-direction:row-reverse'
		}
	},
	data() {
		return {
			entireImg: '',
			topImg: '',
			bottomImg: '',
			allImg: ''
		};
	},
	created() {
		this.imgArr();
	},
	methods: {
		imgArr() {
			let img = this.liquidLayout.img;

			for (let i = 0; i < img.length; i++) {
				switch (img[i].type) {
					case 'entireImg':
						this.entireImg = img[i].imgpic;
						break;
					case 'topImg':
						this.topImg = img[i].imgpic;
						break;
					case 'bottomImg':
						this.bottomImg = img[i].imgpic;
						break;
					case 'allImg':
						this.allImg = img[i].imgpic;
						break;
				}
			}
		}
	}
};
</script>

<style scoped>
.left,
.right {
	box-sizing: border-box;
	height: 100%;
}
.marginRight {
	margin-right: 6upx;
}
.marginLeft {
	margin-left: 6upx !important;
}
image {
	width: 100%;
	display: block;
}

.right image:last-child {
	margin-top: 6upx;
}
</style>

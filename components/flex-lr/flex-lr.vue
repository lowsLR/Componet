<template>
	<view class="container u-f-r-c-b u-f-w" :style="padding">
		<block v-for="(item, index) in flexLr" :key="index">
			<view :style="width">
				<image :src="item.img" lazy-load :style="imgH_bR"></image>
				<view :class="item.content.isflag ? 'u-f-c-c-c' : ''">
					<view v-if="item.content.title" class="title">{{ item.content.title }}</view>
					<view v-if="item.content.text" class="text">{{ item.content.text }}</view>
					<view v-if="item.content.price" class="price">￥{{ item.content.price }}</view>
					<view class="isShop" v-if="item.content.isShop">立即购买</view>
					<!-- 头像信息 -->
					<template v-if="!item.content.isShop">
						<block v-for="(t, i) in item.content.info" :key="i">
							<view class="u-f-r-c-b">
								<view class="u-f-r-c">
									<image :src="t.infopic" lazy-load :style="infoW_H_bR"></image>
									<view class="info-title">{{ t.title }}</view>
								</view>
								<view class="icon iconfont u-f-r-c" :class="t.icon"><text>{{ t.num }}</text></view>
							</view>
						</block>
					</template>
				</view>
			</view>
		</block>
	</view>
</template>

<script>
export default {
	props: {
		// 内边距
		padding:{
			type:String,
			default:''
		},
		// 间距
		width:{
			type:String,
			default:''
		},
		// 图片大小与圆角
		imgH_bR:{
			type:String,
			default:''
		},
		//info的图片大小与圆角
		infoW_H_bR:{
			type:String,
			default:''
		},
		flexLr:Array
	},
	data() {
		return {
			
		};
	}
};
</script>

<style scoped>
.container > view {
	box-sizing: border-box;
	padding: 0 0 20upx 0;
}
.container > view > image {
	width: 100%;
}

.container .title {
	font-size: 30upx;
	color: #000000;
}
.container .text {
	font-size: 20upx;
	color: #ccc;
}
.container .price {
	color: #f50;
	font-size: 26upx;
}
.container .isShop {
	font-size: 24upx;
	font-weight: bold;
	width: 220upx;
	height: 60upx;
	color: #ffffff;
	background: #f50;
	border-radius: 10upx;
	text-align: center;
	line-height: 60upx;
}
.info-title {
	margin-left: 10upx;
}

.container > view > view > view {
	margin-bottom: 10upx;
}
.info-title {
	font-size: 24upx;
	color: #ccc;
}
.icon {
	font-size: 44upx;
	color: #ccc;
}
.icon>text{
	font-size: 20upx;
}
</style>

<template>
	<view class="layout u-f-r-c">
		<!-- 左侧栏 -->
		<view class="l" :style="{ height: windowHeight + 'px' }">
			<scroll-view scroll-y="true" :style="{ height: windowHeight + 'px' }">
				<block v-for="item in orderColumn" :key="item.id">
					<view class="u-w-v-o u-f-c-c-c list" @click="listId(item.id)" :class="item.id == list_id ? 'active' : ''">{{ item.orderName }}</view>
				</block>
			</scroll-view>
		</view>
		<!-- 右侧栏 -->
		<view class="r u-f-1" :style="{ height: windowHeight + 'px' }">
			<swiper class="swiper-box" :style="{ height: windowHeight + 'px' }" @change="tabChange" :current="currentId" vertical="true">
				<swiper-item v-for="item in orderColumn" :key="item.id">
					<!-- swiper-item 获取这个节点就可以了 -->
					<view class="title">{{ item.orderName }}</view>
					<block v-for="(t, i) in item.order" :key="i">
						<!-- 点餐详情 -->
						<order-column-list :item="t" :index="i"></order-column-list>
					</block>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	import orderColumnList from '../order-column-list/order-column-list.vue'
export default {
	components: {
		orderColumnList
	},
	created() {
		this.systemInfHeight();
		// this.$nextTick(() => {
		// 	let view = uni
		// 		.createSelectorQuery()
		// 		.in(this)
		// 		.select('.swiper-item');

		// 	view.boundingClientRect(data => {
		// 		// console.log('得到布局位置信息' + JSON.stringify(data));
		// 		this.swiperH = data.height;
		// 		console.log(this.swiperH, 'swiperH');
		// 	}).exec();
		// });
	},
	data() {
		return {
			list_id: 0,
			currentId: 0,
			//轮播图高度
			swiperH: '',
			// 获取可视高度
			windowHeight: '',
			orderColumn: [
				{
					orderName: '热销1',
					id: 0,
					order: [
						{
							img: '../../static/orderColumn/orderColumn1.jpg',
							title: '牛肉卤粉（干拌）',
							id: 'niuroucufen',
							content: '自家秘方卤制牛肉和粉，配料也是极多',
							xs: '586',
							dianzan: '10',
							pirce: '13',
							qibu: '1碗起步',
							isflag: false //false--选择规格，true--默认是‘添加’
						},
						{
							img: '../../static/orderColumn/orderColumn1.jpg',
							title: '牛肉卤粉（干拌）',
							id: 'niuroucufen',
							content: '自家秘方卤制牛肉和粉，配料也是极多',
							xs: '586',
							dianzan: '10',
							pirce: '13',
							qibu: '1碗起步',
							isflag: true //false--选择规格，true--默认是‘添加’
						},
						{
							img: '../../static/orderColumn/orderColumn1.jpg',
							title: '牛肉卤粉（干拌）',
							id: 'niuroucufen',
							content: '自家秘方卤制牛肉和粉，配料也是极多',
							xs: '586',
							dianzan: '10',
							pirce: '13',
							qibu: '1碗起步',
							isflag: false //false--选择规格，true--默认是‘添加’
						},
						{
							img: '../../static/orderColumn/orderColumn1.jpg',
							title: '牛肉卤粉（干拌）',
							id: 'niuroucufen',
							content: '自家秘方卤制牛肉和粉，配料也是极多',
							xs: '586',
							dianzan: '10',
							pirce: '13',
							qibu: '1碗起步',
							isflag: false //false--选择规格，true--默认是‘添加’
						}
					]
				},
				{
					orderName: '热销2',
					id: 1,
					order: [
						{
							img: '../../static/orderColumn/orderColumn1.jpg',
							title: '牛肉卤粉（干拌）',
							id: 'niuroucufen',
							content: '自家秘方卤制牛肉和粉，配料也是极多',
							xs: '586',
							dianzan: '10',
							pirce: '13',
							qibu: '1碗起步',
							isflag: false //false--选择规格，true--默认是‘添加’
						},
						{
							img: '../../static/orderColumn/orderColumn1.jpg',
							title: '牛肉卤粉（干拌）',
							id: 'niuroucufen',
							content: '自家秘方卤制牛肉和粉，配料也是极多',
							xs: '586',
							dianzan: '10',
							pirce: '13',
							qibu: '1碗起步',
							isflag: true //false--选择规格，true--默认是‘添加’
						},
						{
							img: '../../static/orderColumn/orderColumn1.jpg',
							title: '牛肉卤粉（干拌）',
							id: 'niuroucufen',
							content: '自家秘方卤制牛肉和粉，配料也是极多',
							xs: '586',
							dianzan: '10',
							pirce: '13',
							qibu: '1碗起步',
							isflag: false //false--选择规格，true--默认是‘添加’
						},
						{
							img: '../../static/orderColumn/orderColumn1.jpg',
							title: '牛肉卤粉（干拌）',
							id: 'niuroucufen',
							content: '自家秘方卤制牛肉和粉，配料也是极多',
							xs: '586',
							dianzan: '10',
							pirce: '13',
							qibu: '1碗起步',
							isflag: false //false--选择规格，true--默认是‘添加’
						}
					]
				},
				{
					orderName: '热销3',
					id: 2,
					order: []
				},
				{
					orderName: '热销4',
					id: 3,
					order: []
				},
				{
					orderName: '热销5',
					id: 4,
					order: []
				},
				{
					orderName: '热销6',
					id: 5,
					order: []
				},
				{
					orderName: '热销7',
					id: 6,
					order: []
				},
				{
					orderName: '热销8',
					id: 7,
					order: []
				},
				{
					orderName: '热销9',
					id: 8,
					order: []
				},
				{
					orderName: '热销10',
					id: 9,
					order: []
				},
				{
					orderName: '热销11',
					id: 10,
					order: []
				},
				{
					orderName: '热销12',
					id: 11,
					order: []
				},
				{
					orderName: '热销13',
					id: 12,
					order: []
				},
				{
					orderName: '热销14热销14热销14热销14热销14',
					id: 13,
					order: []
				}
			]
		};
	},
	methods: {
		systemInfHeight() {
			uni.getSystemInfo({
				success: res => {
					this.windowHeight = res.windowHeight - uni.upx2px(100);
				}
			});
		},
		listId(id) {
			// console.log(id, '---id');
			this.list_id = id;
			this.currentId = id;
		},
		tabChange(e) {
			// console.log(e, '---e');
			this.list_id = e.detail.current;
		}
	}
};
</script>

<style scoped>
.layout {
}
.l {
	width: 160upx;
}
.l view {
	width: 100%;
	height: 100upx;
	background: #f5f5f5;
	color: #666666;
	font-size: 25upx;
}
.list.active {
	color: #333;
	background: #ffffff;
}

</style>

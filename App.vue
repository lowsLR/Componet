<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/* 引入官方css库 */
	@import './common/uni.css';
	/* 公共样式 */
	@import './common/common.css';
	/* 引入自定义图标库 */
	@import './static/font/iconfont.css';
	page{ 
		background: #FFFFFF; 
		height: 100%;
	}
	::-webkit-scrollbar{
		display: none;
	}
</style>

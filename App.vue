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
		},
		onError(err) {
			console.log('异常：',err)
		}
	}
</script>

<style>
	/*每个页面公共css */
	@import "@/static/fonts/iconfont.css";
	/* @import url("./static/fonts/iconfont.css"); */
	@import "~@/static/fonts/font-cop.css";
	.box1{
		color: #fff;
	}
</style>

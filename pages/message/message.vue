<template>
	<view>
		样式学习
		<view class="box1">
			测试文字
			<text>123</text>
		</view>
		<view class="iconfont school-weixin my-icon">
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	@import url("./index.css");
.box1{
	width: 375rpx;
	height: 375rpx;
	/* font-size: 16rpx; */
	background-color: pink;
	background-color: $global-color;
	text{
		font-weight: bold;
		color: pink;
	}
}
.my-icon{
	font-size: 80rpx;
	color: #4CD964;
}
</style>

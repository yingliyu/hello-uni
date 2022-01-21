<template>
	<view>
		<!-- 	样式学习
		<view class="box1">
			测试文字
			<text>123</text>
		</view> -->
		<text class="iconfont school-weixin my-icon" />
		<i class="abs-icon fc fc-question-o"></i>
		
		<view>
			<uni-calendar ref="calendar" :selected='selectedList' @change="change" :insert="false" @confirm="confirm" />
			<button type='primary' @click="open">打开日历</button>
		</view>
		<!-- 	<uni-calendar :insert="true" :lunar="true" :start-date="'2019-3-2'" :end-date="'2022-5-20'"
			:selected='selectedList' @change="change" /> -->

		<!--#ifdef H5-->
		<view>只希望在H5中显示</view>
		<!--#endif-->
		<!--#ifdef MP-WEIXIN-->
		<view>只希望在小程序中显示</view>
		<!--#endif-->
		<button type="primary" @click="uploadFile">上传图片</button>

		<image v-for="(item,index) in imgList" :src="item" :key='item' mode="aspectFit" @click="previewImg(item)">
		</image>
		<button type="default" @click="switchTest">切换test组件显隐</button>
		<test v-if="flag" @customEvent='getNum' name='哈哈哈' />
		这是子组件传过来的值{{num}}
		<test-a />
		<test-b />
	</view>
</template>

<script>
	import test from '../../components/test.vue'
	import testA from '../../components/a.vue'
	import testB from '../../components/b.vue'
	export default {
		components: {
			test,
			"test-a": testA,
			"test-b": testB
		},
		data() {
			return {
				imgList: [],
				flag: true,
				num: 0,
				selectedList: [{
					date: '2022-01-20',
					info: '签到',
				}]
			}
		},
		onLoad() {
			// #ifdef H5 || APP-PLUS
			console.log('Here is H5！')
			// #endif
			// #ifdef MP-WEIXIN
			console.log('Here is MP-WEIXIN！')
			// #endif
		},
		methods: {
			open() {
				this.$refs.calendar.open();
			},
			confirm(e) {
				console.log('confirm', e);
			},
			change(e) {
				console.log('change===', e)
			},
			getNum(num) {
				console.log(num)
				this.num = num
			},
			// 上传图片
			uploadFile() {
				uni.chooseImage({
					count: 5,
					success: (res) => {
						console.log(res)
						this.imgList = res.tempFilePaths
					}
				})
			},
			previewImg(current) {
				uni.previewImage({
					current,
					urls: this.imgList,
					loop: true, // 仅对APP生效
					indicator: 'number' // 仅对APP生效
				})
			},
			switchTest() {
				this.flag = !this.flag
			}
		}
	}
</script>

<style lang="scss">
	@import url("./index.css");

	view {
		/* #ifdef H5 */
		color: red;
		/* #endif */
		/* #ifdef MP-WEIXIN */
		color: green;
		/* #endif */
	}

	.box1 {
		width: 375rpx;
		height: 375rpx;
		/* font-size: 16rpx; */
		background-color: pink;
		background-color: $global-color;

		text {
			font-weight: bold;
			color: pink;
		}
	}

	.my-icon {
		font-size: 80rpx;
		color: #4CD964;
	}
</style>

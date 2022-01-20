<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image> -->
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<view class="list-wrapper" v-for="(item,index) in list" :key='index+item'>
			{{index}}-我是{{item}}
		</view>
		<button type="primary" @click="pullDownHandle">刷新数据</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '技术岗位列表',
				list:[
					"前端","JAVA","UI","Big Data","云计算","人工智能","JAVA","UI","Big Data","云计算","人工智能"
				]
			}
		},
		onLoad(options) {
			console.log('页面加载了onLoad',options)
		},
		onShow() {
			console.log('页面显示了onShow')
		},
		onReady() {
			console.log('页面初次渲染完成了onReady')
		},
		onHide() {
			console.log('页面隐藏了onHide')
		},
		onPullDownRefresh() {
			console.log('你下拉页面了...')
			setTimeout(()=>{
				this.list=['balabala',"JAVA","UI","Big Data"]
				uni.stopPullDownRefresh()
			},2000)
		},
		onReachBottom() {
			console.log('我到底了，不能再拉了~')
		},
		methods: {
			pullDownHandle(){
				uni.startPullDownRefresh()
			}
		}
	}
</script>

<style lang="scss">
	.content {
		// display: flex;
		// flex-direction: column;
		// align-items: center;
		// justify-content: center;
		padding: 10rpx;
		.list-wrapper{
			height: 100px;
			// background-color: pink;
		}
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>

<template>
	<view>
		<text space="emsp">{{flag?'真true! ':'假false! '}} </text>
		<text>{{msg+" !!!"}}</text>
		
		<navigator url="../detail/detail?id=6&name=lemon" >
			跳转至详情页Switch
		</navigator>
		<navigator url="../message/message" open-type="switchTab">跳转至TabBar中的新闻页-></navigator>
		<navigator url="../detail/detail" open-type="redirect">跳转至详情页Redirect-></navigator>
		
		<image :src="imgUrl" mode="aspectFit"></image>
		<button type="primary" @click="toDetailPage">跳转至详情页</button>
		<button type="primary" @click="toNewsPage">跳转至TabBar新闻页</button>
		<button type="primary" @click="redirectToDetailPage">跳转至详情页并关闭当前页</button>
		<view v-for="item in list" :key='item.id'>
			序号：{{item.id}}- 姓名：{{item.name}}-年龄：{{item.age}}
		</view>
		<button type="primary" @click="clickHandle(10,$event)">Button</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				msg:'hello lemon',
				flag:true,
				imgUrl:"../../static/image/ddcat.png",
				list:[
					{
						name:'叮当猫',
						age:18,
						id:1
					},
					{
						name:'凯蒂猫',
						age:8,
						id:2
					},
					{
						name:'小浣熊',
						age:4,
						id:3
					}
				]
			}
		},
		methods: {
			clickHandle(num,event){
				console.log('click me',num,event)
			},
			toDetailPage(){
				uni.navigateTo({
					url:'../detail/detail?id=6&name=lemon'
				})
			},
			toNewsPage(){
				uni.switchTab({
					url:'../message/message'
				})
			},
			redirectToDetailPage(){
				// 关闭当前页面，跳转到应用内的某个页面。
				uni.redirectTo({
					url:'../detail/detail'
				})
			}
		},
		onUnload() {
			console.log('页面卸载了！！！')
		}
	}
</script>

<style>
	view{
		padding: 20rpx;
	}
navigator{
	color: #007AFF;
	text-decoration: underline;
	line-height: 60rpx;
}
image{
	width: 200rpx;
	height: 200rpx;
}
</style>

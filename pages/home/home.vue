<template>
	<view>
		数据绑定
		<view>{{msg+" !!!"}}</view>
		<view>{{1+1}}</view>
		<view>{{flag?'真true':'假false'}}</view>
		<image :src="imgUrl" mode="aspectFit"></image>
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
			}
		}
	}
</script>

<style>

</style>

<template>
	<view>
		<button type="primary" @click="getHandle">发送Get请求</button>
		<button type="default" @click="saveData">数据存储</button>
		<button type="primary" @click="getData">数据获取</button>
		<button type="primary" @click="delData">移除数据</button>
	
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
			getHandle(){
				uni.request({
					url:'https://api-hmugo-web.itheima.net/api/public/v1/home/swiperdata',
					success(res) {
						console.log(res)
					}
				})
			},
			saveData(){
				// uni.setStorage({
				// 	key:'id',
				// 	data:100,
				// 	success() {
				// 		console.log('存储成功！')
				// 	}
				// })
				uni.setStorageSync('id',80)
			},
			getData(){
				// uni.getStorage({
				// 	key:"id",
				// 	success(res) {
				// 		console.log('获取成功：',res)
				// 	}
				// })
				const res = uni.getStorageSync('id')
				console.log(res)
			},
			delData(){
				// uni.removeStorage({
				// 	key:'id',
				// 	success() {
				// 		console.log('删除成功')
				// 	}
				// })
				uni.removeStorageSync('id')
			}
		}
	}
</script>

<style>

</style>

<template>
	<view>
		这是test组件！！！父组件传过来的name：{{name}}
		<view id="myView">my view</view>
		<button type="default" @click="getNum">给父组件传值</button>
	</view>
</template>

<script>
	export default {
		name: "test",
		props:['name'],
		data() {
			return {
				num: 123,
				timer: null
			};
		},
		methods:{
			getNum(){
				console.log('给父组件传值')
				this.$emit('customEvent',this.num)
			}
		},
		beforeCreate() {
			console.log('实例开始初始化了！', this.num)
		},
		created() {
			console.log('实例初始化完成', this.num)
			// this.timer=setInterval(() => {
			// 	console.log('执行定时器！')
			// }, 1000)
		},
		beforeMount() {
			// 仅h5支持getElementById
			// console.log('beforeMount', document?.getElementById('myView'))
		},
		mounted() {
			// 仅h5支持getElementById
			// console.log('mounted', document?.getElementById('myView'))
		},
		destroyed() {
			console.log('组件销毁了！')
			// 清除定时器
			clearInterval(this.timer)
		}
	}
</script>

<style>

</style>

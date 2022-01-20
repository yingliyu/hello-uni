<template>
	<view>
		<text>hello &amp; text</text>
		<view>
			<text selectable space='ensp'>hello text</text>
		</view>

		<view>
			<text selectable space="nbsp">hello text</text>
		</view>

		<view class="wrapper" hover-class="wrapper-active">
			<view class="box" :hover-start-time='10' :hover-stay-time='2000' hover-stop-propagation
				hover-class='box-active'>
				<text selectable space="emsp" style="font-size: 18px;">hello text</text>
			</view>
		</view>
		<button>按钮</button>
		<button size="mini">按钮</button>
		<button type="primary">按钮</button>
		<button type="primary" disabled>按钮</button>
		<button type="primary" plain>按钮</button>
		<button type="primary" loading>按钮</button>
		<image src="http://destiny001.gitee.io/image/cxk.gif" mode="aspectFill"></image>
		<image src="http://destiny001.gitee.io/image/cxk.gif" mode="aspectFit"></image>
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

<style>
	.wrapper {
		width: 100px;
		height: 100px;
		background-color: orange;
	}

	.wrapper-active {
		background-color: green;
	}

	.box {
		width: 100px;
		height: 50px;
		background-color: pink;
	}

	.box-active {
		background-color: #007AFF;
	}
</style>

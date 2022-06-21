<template>
	<view>
		<view @tap="demoClick" class="title">
			首页
		</view>
	</view>
</template>

<script>
	export default {
		methods: {
			demoClick() {
				// #ifdef APP-PLUS
				// 通过 id 获取 nvue 子窗体
				const subNvue = uni.getSubNvueById('demo-popup')
				subNvue.show('slide-in-out', 300, function() {
					console.log('subNvue的回调');
				})

				setTimeout(() => {
					subNvue.hide('fade-out', 300)
				}, 2000)
				// #endif
				// #ifdef H5
				console.log('测试一下h5页面功能');
				// #endif
			}
		}
	}
</script>

<style lang="scss" scoped>
	.title {
		font-size: 30px;
	}
</style>

<template>
	<view class="navigat" :style="{ backgroundColor: bgColor, backgroundImage: bgImage }">
		<image class="bar-left" @tap="naviback()" src="/static/images/user/close.png" mode="aspectFill"></image>
		<text class="bar-right" @tap="jump(url)">{{ text }}</text>
	</view>
</template>
<script>
export default {
	props: {
		// 自定义导航栏背景颜色
		bgColor: {
			type: String,
			default: '#ffffff'
		},
		// 自定义导航栏背景渐变,例如:linear-gradient(to top, #36d4fc, #64affb)
		bgImage: {
			type: String,
			default: ''
		},
		url: {
			type: String,
			default: ''
		}
	},
	data() {
		return {
			text: '注册'
		};
	},
	methods: {
		naviback() {
			// 根据逻辑业务跳转相应页面
			uni.navigateBack();
		},
		jump(args) {
			//url默认为字符串格式，请加上String类型，以免控制台抛错
			uni.navigateTo({
				url: String(args)
			});
		}
	}
};
</script>

<style>
.navigat {
	width: 750upx;
	height: 88upx;
	padding: 0 24upx;
	flex-direction: row;
	align-items: center;
	justify-content: space-between;
}
.bar-left {
	width: 42upx;
	height: 42upx;
	padding: 5upx;
}
.bar-right {
	font-size: 32upx;
	color: #a6a6a6;
}
</style>

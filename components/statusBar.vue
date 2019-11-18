<template>
	<view class="statusBar" :style="{ height: statusBarHeight + 'px', backgroundColor: bgColor,bgColor, backgroundImage: bgImage }"></view>
</template>

<script>
export default {
	props: {
		// 自定义状态栏背景颜色
		bgColor: {
			type: String,
			default: '#ffffff'
		},
		// 自定义状态栏背景渐变,例如:linear-gradient(to top, #36d4fc, #64affb)
		bgImage: {
			type: String,
			default: ''
		},
		// 自定义状态栏高度
		statusBarHeight: {
			type: Number,
			default: 0
		}
	},
	data() {
		return {};
	}
};
</script>

<style></style>

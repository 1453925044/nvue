<script>
export default {
	onLaunch() {
		console.log('App Launch');
	},
	onShow() {
		console.log('App Show');
	},
	onHide() {
		console.log('App Hide');
	}
};
</script>

<style>
/* input表单placeholder样式 */
.p-active {
	color: #cccccc;
}
/* 字体包 */
@font-face {
	font-family: medium;
	font-weight: normal;
	font-style: normal;
	font-display: swap;
	src: url('https://www.chinabdc.cn:8092/H5/font/PingFangSC-Medium.ttf') format('truetype');
}
/* 按钮样式 */
.btn {
	width: 656upx;
	height: 90upx;
	line-height: 90upx;
	text-align: center;
	font-size: 32upx;
	border-radius: 12upx;
	color: #ffffff;
}

.btn-gradient {
	background-image: linear-gradient(to top, #36d4fc, #64affb);
	color: white;
}
.btn-gradient:active {
	background-image: linear-gradient(to top, #36d4fc, #409eff);
}

.btn-nomal {
	background-color: #26a2ff;
	color: white;
}
.btn-nomal:active {
	background-color: #2071ab;
	color: white;
}
.btn-danger {
	background-color: #f56c6c;
	color: white;
}
.btn-danger:active {
	background-color: #f78989;
	color: white;
}
.btn-default {
	background-color: #409eff;
}
.btn-default:active {
	background-color: #66b1ff;
}

.btn-nomalborder {
	border-width: 3upx;
	border-radius: 5upx;
	border-color: #26a2ff;
}
.btn-nomalborder:active {
	border-width: 3upx;
	border-radius: 5upx;
	border-color: #2071ab;
}
.btn-dangerborder {
	border-width: 3upx;
	border-radius: 5upx;
	border-color: #ef4f4f;
}
.btn-dangerborder:active {
	border-width: 3upx;
	border-radius: 5upx;
	border-color: #ab2048;
}
.btn-defaultborder {
	border-width: 3upx;
	border-radius: 5upx;
	border-color: lightslategray;
}
.btn-defaultborder:active {
	background-color: #f6f6e5;
}
</style>

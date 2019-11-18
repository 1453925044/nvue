<template>
	<view class="regist">
		<!-- 表单验证 -->
		<form class="from" @submit="formSubmit" @reset="formReset">
			<!-- 手机号码 -->
			<view class="cell"><input class="input" type="number" :maxlength="11" v-model="phone" name="phone" placeholder="请输入手机号" placeholder-class="p-active" /></view>
			<!-- 验证码 -->
			<view class="cell">
				<input class="input" type="number" :maxlength="6" v-model="yzm" name="yzm" placeholder="请输入验证码" placeholder-class="p-active" />
				<button type="default" :disabled="disable" class="send-btn" @tap="getMsg()" :class="{ isColor: disable == true }">{{ count }}{{ btnMsg }}</button>
			</view>
			<!-- 设置密码 -->
			<view class="cell"><input class="input" v-model="pwd" :maxlength="18" type="password" name="pwd" placeholder="请设置6~18位密码" placeholder-class="p-active" /></view>
			<view class="agreement">
				<view class="xy">为保障您的隐私权益,请认真阅读以下协议</view>
				<view class="xy">
					<navigator hover-class="none" class="navigate" url="/pages/systemSet/statement/privacy">《平台隐私政策》</navigator>
					及
					<navigator hover-class="none" class="navigate" url="/pages/systemSet/statement/userPolicy">《平台用户服务协议》</navigator>
				</view>
			</view>
			<!-- 点击注册 -->
			<view class="sure"><button class="btn btn-gradient" formType="submit">同意协议并注册</button></view>
		</form>
	</view>
</template>

<script>
export default {
	data() {
		return {
			phone: '',
			disable: false,
			yzm: '',
			pwd: '',
			btnMsg: '',
			count: '获取验证码',
			timer: null
		};
	},
	methods: {
		// 发送短信验证码
		getMsg() {
			this.disable = true;
			this.btnMsg = 's重发';
			const TIME_COUNT = 60;
			if (!this.timer) {
				this.count = TIME_COUNT;
				this.timer = setInterval(() => {
					if (this.count > 0 && this.count <= TIME_COUNT) {
						this.count-- + 's';
					} else {
						clearInterval(this.timer);
						this.timer = null;
						this.count = '重新获取';
						this.btnMsg = '';
						this.disable = false;
					}
				}, 1000);
				uni.showToast({
					title: '发送成功'
				});
			}
		},
		//注册验证
		formSubmit(e) {
			console.log(e);
		}
	}
};
</script>

<style scoped lang="less">
.regist {
	width: 100%;
	padding: 0 42upx;
	box-sizing: border-box;
	.from {
		width: 100%;
		.cell::after {
			position: absolute;
			content: '';
			left: 0;
			bottom: 0;
			width: 200%;
			height: 1upx;
			transform: scale(0.5);
			transform-origin: left top;
			background-color: #cccccc;
		}

		.cell {
			position: relative;
			width: 100%;
			height: 115upx;
			display: flex;
			justify-content: space-between;
			align-items: center;

			.input {
				height: 100%;
				font-size: 28upx;
				color: #181818;
			}
			.send-btn {
				width: 138upx;
				line-height: 50upx;
				height: 50upx;
				font-size: 28upx;
				padding: 0upx;
				margin: 0;
				background: rgba(0, 0, 0, 0);
				color: #888888;
			}
			.send-btn::after {
				border: none;
			}
			.isColor {
				color: #409eff;
			}
		}
		.agreement {
			width: 100%;
			margin-top: 38upx;
			.xy {
				display: flex;
				align-items: center;
				font-size: 26upx;
				color: #cccccc;
				margin-top: 24upx;
				.navigate {
					padding: 10upx 0;
					color: #cccccc;
					text-decoration: underline;
				}
			}
		}
		.sure {
			width: 100%;
			margin: 160upx auto 0upx;
			.btn::after {
				border: none;
			}
		}
	}
}
</style>

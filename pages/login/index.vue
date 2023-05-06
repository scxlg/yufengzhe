<template>
	<view class="login-warp">
		<view>
			<view class="title">专业技术人员申报服务平台</view>
			<view class="ipt">
				<input type="text" placeholder="NMSX00012339">
			</view>
			<view class="ipt">
				<input type="text" placeholder="姓名">
			</view>
			<view class="ipt">
				<input type="text" placeholder="手机号">
			</view>
			<view class="ipt ipt1">
				<input type="text" placeholder="短信验证码">
				<button class="mini-btn" type="primary" size="mini">发送验证码</button>
			</view>
			<view style="margin-top: 60px;">
				<button class="login-btn" type="primary" @click="loginFun">查询</button>
			</view>
			<!-- <view class="img-warp">
				<image src="../../static/loginimg.png"></image>
			</view> -->
		</view>
	</view>
</template>

<script setup>
	const loginFun = () => {
		uni.navigateTo({
			url:'/pages/index/index'
		})
	}
</script>

<style lang="scss">
.login-warp{
	box-shadow: 0px 0px 6px 1px rgba(161,159,188,0.35);
	border-radius: 4px 4px 4px 4px;
	background: linear-gradient(35deg, #AAB7FF 0%, #ABB8FF 20%, #FFFFFF 100%);
	display: flex;
	flex-direction: column;
	align-items: center;
	&>view{
		height: 1624px;
		background: url('../../static/login.png') no-repeat 0 190px;
		.title{
			width: 528px;
			height: 62px;
			font-size: 44px;
			font-family: PingFang SC-Medium, PingFang SC;
			font-weight: 500;
			color: #3491FA;
			margin: 133px auto 77px;
		}
		.ipt{
			width: 666px;
			background-color: #FFFFFF;
			margin-bottom: 32px;
			border-radius: 4px 4px 4px 4px;
			input{
				flex: 1;
				height: 47px;
				background-color: #FFFFFF;
				padding: 23px 24px 20px 32px;
				font-size: 32px;
				font-family: PingFang SC-Regular, PingFang SC;
				font-weight: 400;
				color: #999999;
			}
		}
		.ipt1{
			display: flex;
			justify-content: space-between;
			align-items: center;
			.mini-btn{
				// width: 130px;
				margin-right: 24px;
				height: 62px;
				line-height: 62px;
				font-size: 26px;
				font-family: PingFang SC-Regular, PingFang SC;
				font-weight: 400;
				color: #FFFFFF;
			}
		}
	}
	.login-btn{
		height: 90px;
		border-radius: 4px 4px 4px 4px;
		font-size: 34px;
		font-family: PingFang SC-Medium, PingFang SC;
		font-weight: 500;
		color: #FFFFFF;
	}
}
</style>

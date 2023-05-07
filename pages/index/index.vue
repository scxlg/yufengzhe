<template>
	<view class="content">
		<view class="info-warp">
			<image src="../../static/tx.png"></image>
			<view>
				<view class="info-name">姓名：{{name}}</view>
				<view>服务公司代码：{{code}}</view>
			</view>
		</view>
		<view class="main-warp">
			<view @click="toPage('xyxx')">
				<view>学员信息</view>
			</view>
			<view @click="toPage('zcsb')">
				<view>职称申报</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				name: '李xx',
				code:'NMSX00012339'
				
			}
		},
		onLoad() {

		},
		methods: {
			toPage(_type){
				switch (_type){
					case 'xyxx':
						uni.navigateTo({
							url:'/pages/xyxx/index'
						})
						break;
					case 'zcsb':
						uni.navigateTo({
							url:'/pages/zcsb/index'
						})
						break;
					default:
						break;
				}
			}
		}
	}
</script>

<style lang="scss">
	$font-family:'PingFang SC-Bold, PingFang SC';
	$browser-default-font-size: 75px;//变量的值可以根据自己需求定义
	html {
		    font-size: $browser-default-font-size;
		}
	@function pxTorem($px){//$px为需要转换的字号
	    @return  $px / $browser-default-font-size  * 2rem;
	}
	.content{
		height: 100vh;
	}
	.info-warp{
		// height: 320px;
		min-width: pxTorem(750px);
		background: linear-gradient(182deg, #3491FA 0%, #FFFFFF 100%);
		display: flex;
		padding: pxTorem(90px) 0 pxTorem(82px) pxTorem(48px);
		image{
			max-width: pxTorem(148px);
			max-height: pxTorem(148px);
		}
		&>view{
			font-family: $font-family;
			height: pxTorem(148px);
			margin-left: pxTorem(42px);
			color: #fff;
			font-size: pxTorem(30px);
			display: flex;
			flex-direction: column;
			justify-content: center;
			.info-name{
				margin-bottom: pxTorem(23px);
			}
		}
	}
	.main-warp{
		padding: pxTorem(12px) pxTorem(30px) 0;
		display: flex;
		flex-direction: column;
		align-items: center;
		&>view{
			min-width: pxTorem(690px);
			height: pxTorem(240px);
			font-family: $font-family;
			font-weight: bold;
			font-size: pxTorem(36px);
			color: #333;
			// padding: 42px 0 0 48px;
			margin: pxTorem(12px) auto;
			background: url('../../static/xyxx.png') no-repeat;
			background-size: 100%;
			view{
				margin: pxTorem(42px) 0 0 pxTorem(48px);
			}
		}
		&>view:last-child{
			background: url('../../static/zcsb.png') no-repeat;
			background-size: 100%;
		}
	}
</style>

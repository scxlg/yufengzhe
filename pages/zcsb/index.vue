<template>
	<view>
		<Header title="职称申报" right="新增申报"/>
		<view class="main" >
			<view v-for="item in 3">
				<view>
					<view>
						<text class="title">编号：20232258556</text>
						<button class="mini-btn" type="primary" size="mini" @click="isShowFun">{{!isShow?'展开':'收起'}}</button>
					</view>
					<view>
						<view>评审资格：工程技术人...</view>
						<view>申请日期：2023-10-20 20：00</view>
						<view>申请截至时间：2023-10-22 10：00</view>
					</view>
				</view>
				<view  class="hide-info" v-if="isShow" ref="showText">
					<view>
						<view>申请人</view>
						<view>李XX</view>
					</view>
					<view>
						<view>工作单位</view>
						<view>成都XXX有限公司</view>
					</view>
					<view>
						<view>评审委员会</view>
						<view>工程技术副高级职称市工程师协会评审委员会</view>
					</view>
					<view class="info-btn">
						<view>状态</view>
						<view>主任审核</view>
						<button @click="ProgressDetails">进度详情</button>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script setup>
	import Header from '../../components/Header/index.vue'
	import { ref, getCurrentInstance, nextTick } from "vue";
	let isShow = ref(false)
	const { proxy } = getCurrentInstance()
	const isShowFun = (item) => {
		isShow.value = !isShow.value
	}
	const ProgressDetails = () => {
		uni.navigateTo({
			url:'/pages/ProgressDetails/index'
		})
	}
</script>

<style lang="scss">
	$browser-default-font-size: 75px;//变量的值可以根据自己需求定义
		html {
			    font-size: $browser-default-font-size;
			}
		@function pxTorem($px){//$px为需要转换的字号
		    @return  $px / $browser-default-font-size  * 2rem;
		}
.main{
	padding: pxTorem(20px) pxTorem(30px) pxTorem(30px);
	background-color: #f5f5f5;
	&>view{
		margin-bottom: pxTorem(24px);
		font-size: pxTorem(30px);
		font-family: PingFang SC-Regular, PingFang SC;
		font-weight: 400;
		color: #333333;
		line-height: pxTorem(48px);
		.title{
			font-size: pxTorem(34px);
			font-weight: bold;
		}
		.mini-btn{
			font-size: pxTorem(30px);
			font-family: PingFang SC-Medium, PingFang SC;
			font-weight: 500;
		}
		&>view{
			margin-bottom: 1px;
			&>view{
				padding: pxTorem(32px);
				background-color: #fff;
				margin-bottom: 1px;
			}
			&>view:first-child{
			display: flex;
			align-items: center;
			position: relative;
			button{
				position: absolute;
				right: pxTorem(32px);
			}
		}
		}
	}
	.hide-info{
		&>view{
			display: flex;
			align-items: center;
			&>view:first-child{
				width: pxTorem(173px);
				margin-right: pxTorem(72px);
			}
			&>view:last-child{
				flex: 1;
			}
		}
	}
	.info-btn{
		position: relative;
		button{
			position: absolute;
			right: pxTorem(30px);
			width: pxTorem(200px);
			height: pxTorem(54px);
			background: #EEF1F9;
			border-radius: 4px 4px 4px 4px;
			font-size: pxTorem(30px);
			line-height: pxTorem(54px);
			font-family: PingFang SC-Medium, PingFang SC;
			font-weight: 500;
			color: #3491FA;
		}
	}
}
</style>
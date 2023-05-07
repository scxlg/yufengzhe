<template>
	<view>
		<Header title="进度详情" />
		<view class="main" >
			<view class="">
				<uni-steps :options="list" active-color="#007AFF" :active="active" direction="column">
				</uni-steps>
			</view>
		</view>
	</view>
</template>

<script setup>
	import Header from '../../components/Header/index.vue'
	import { ref } from "vue";
	let active = ref(2)
	let list = ref([
		{title: `填写中 2018-11-11`,desc: `单位名称：成都XXX有限公司
		联系人：李XX
		联系方式：18888888888`,}, 
		{title: '填写中 2018-11-11',desc: `单位名称：成都XXX有限公司
		联系人：李XX
		联系方式：18888888888`}, 
		{title: '填写中 2018-11-11',desc: `单位名称：成都XXX有限公司
		联系人：李XX
		联系方式：18888888888`}, 
		{title: '待单位上报 未开始',desc: ''},
		{title: '待单位上报 未开始',desc: ''}
		])
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
.main{
	padding: pxTorem(20px) pxTorem(30px) pxTorem(30px);
	background-color: #f5f5f5;
	&>view{
		background-color: #fff;
		margin-bottom: pxTorem(24px);
		padding: pxTorem(32px);
	}
}
:deep(.uni-steps__column-desc){
	padding: pxTorem(18px) pxTorem(119px) pxTorem(14px) pxTorem(30px);
	width: pxTorem(511px);
	height: pxTorem(168px);
	background: #F2F6FF;
	border-radius: 4px 4px 4px 4px;
	font-size: pxTorem(28px);
	font-family: PingFang SC-Regular, PingFang SC;
	font-weight: 400;
	color: #333333;
	line-height: pxTorem(48px);
}
:deep(.uni-steps__column-title){
	margin: pxTorem(60px) 0 pxTorem(8px);
	span{
		width: pxTorem(102px);
		font-size: pxTorem(34px);
		font-family: PingFang SC-Bold, PingFang SC;
		font-weight: bold;
		color: #333333;
	}
}
</style>

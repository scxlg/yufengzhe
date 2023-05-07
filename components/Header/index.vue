<template>
	<view>
		<uni-nav-bar  left-icon="left" :title="props.title" :right-text="props.right" @clickLeft="back"  @clickRight="addFun"/>
	</view>
</template>

<script setup>
	let props = defineProps({
		title:String,
		right:String
	})
	const back = () => {
		uni.navigateBack()
	}
	const addFun = () => {
		if(props.right){
			uni.navigateTo({
				url:'/pages/addzcsb/index'
			})
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
:deep(.uni-nav-bar-text){
	font-size: pxTorem(34px);
	font-family: PingFang SC-Medium, PingFang SC;
	font-weight: 500;
	color: #333333;
}
:deep(.uni-navbar__header){
	height: pxTorem(88px) !important;
	line-height: pxTorem(88px);
}
:deep(.uni-icons,.uniui-left){
	font-size: pxTorem(40px) !important;
}
:deep(.uni-navbar__header-btns,.uni-navbar__header-btns-right){
	width: pxTorem(128px) !important;
}
:deep(.uni-navbar--border){
	border: 0;
}
:deep(.uni-nav-bar-right-text){
	font-size: pxTorem(32px);
	font-family: PingFang SC-Medium, PingFang SC;
	font-weight: 500;
	color: #3491FA !important;
}
</style>
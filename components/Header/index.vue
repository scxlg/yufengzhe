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
:deep(.uni-nav-bar-text){
	font-size: 34px;
	font-family: PingFang SC-Medium, PingFang SC;
	font-weight: 500;
	color: #333333;
}
:deep(.uni-navbar__header){
	height: 88px !important;
	line-height: 88px;
}
:deep(.uni-icons,.uniui-left){
	font-size: 40px !important;
}
:deep(.uni-navbar__header-btns,.uni-navbar__header-btns-right){
	width: 128px !important;
}
:deep(.uni-navbar--border){
	border: 0;
}
:deep(.uni-nav-bar-right-text){
	font-size: 32px;
	font-family: PingFang SC-Medium, PingFang SC;
	font-weight: 500;
	color: #3491FA !important;
}
</style>
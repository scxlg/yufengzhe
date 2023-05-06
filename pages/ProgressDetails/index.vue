<template>
	<view>
		<Header title="进度详情" />
		<view class="main" >
			<view class="">
				<uni-steps :options="list" active-color="#007AFF" :active="active" direction="column">
					<template>
						<view>hhh</view>
					</template>
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
.main{
	padding: 20px 30px 30px;
	background-color: #f5f5f5;
	&>view{
		background-color: #fff;
		margin-bottom: 24px;
		padding: 32px;
	}
}
:deep(.uni-steps__column-desc){
	padding: 18px 119px 14px 30px;
	width: 511px;
	height: 168px;
	background: #F2F6FF;
	border-radius: 4px 4px 4px 4px;
	opacity: 1;
	font-size: 28px;
	font-family: PingFang SC-Regular, PingFang SC;
	font-weight: 400;
	color: #333333;
	line-height: 48px;
}
</style>

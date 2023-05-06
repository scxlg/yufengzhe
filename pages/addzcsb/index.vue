<template>
	<view>
		<Header title="学员信息" />
		<view class="main">
			<Form type='0'/>
		</view>
	</view>
</template>

<script setup>
	import Header from '../../components/Header/index.vue'
	import Form from '../../components/Form/index.vue'
</script>

<style lang="scss">
.main{
	padding: 20px 30px 30px;
	background-color: #f5f5f5;
}
</style>

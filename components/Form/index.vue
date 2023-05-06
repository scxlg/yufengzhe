<template>
	<view class="form-warp">
		<view class="form-warp-top">
			<view>
				<view class="text-type">基本信息</view>
				<view v-if="props.type==1">
					<button class="mini-btn mini-btn1" type="primary" size="mini">修改</button>
					<button class="mini-btn" type="primary" size="mini" @click="isShowFun">{{!isShow?'展开':'收起'}}</button>
				</view>
				<view v-else>
					<button class="mini-btn" type="primary" size="mini">保存</button>
				</view>
			</view>
			<view v-for="item in data" key="item.type">
				<view class="text-type">{{item.type}}</view>
				<view v-if="item.type == '性别'">
					<radio-group @change="radioChange" style="width: 320px;display: flex;justify-content: space-between;" class="text-type text-value">
						<label>
							<radio value="男"/><span style="margin-left: 20px;">男</span>
						</label>
						<label>
							<radio value="女"/><span style="margin-left: 20px;">女</span>
						</label>
					</radio-group>
				</view>
				<view class="text-type text-value" v-else>{{item.value}}</view>
				<image v-if="item.icon" :src="item.icon"></image>
			</view>
		</view>
		<view class="form-warp-bottom" v-for="item in userElse" :key="item">
			<text class="text-type" style="width: 288px;">{{item}}</text>
			<button class="mini-btn" type="primary" size="mini">编辑</button>
		</view>
	</view>
</template>

<script setup>
import { ref } from "vue";
	let data = ref([
		{type:'姓名',value:'李XX'},
		{type:'曾用名',value:'Windir'},
		{type:'性别',value:''},
		{type:'身份证号',value:511111111111111111},
		{type:'生日',value:'1998-10-10',icon:'../../static/right.png'},
		{type:'参加工作时间',value:'2010-10-10'},
		{type:'线工作单位',value:'成都KKKK有限公司'},
		{type:'职务',value:'技术负责人'},
		{type:'档案所在地',value:'市外'},
		{type:'档案查询情况',value:'请上传',icon:'../../static/add.png'},
		{type:'参保情况',value:'请上传',icon:'../../static/add.png'},
		{type:'人员类别',value:'私营企业流动人员'}
	])
	let userElse = ref(['学历学位','现有资格','进修或者培训经历'])
	let props = defineProps({
		type:String
	})
	let isShow = ref(false)
	const isShowFun = () => {
		isShow.value = !isShow.value
	}
</script>

<style lang="scss">
$font-family:'PingFang SC-Bold, PingFang SC';
.form-warp{
	min-width: 750px;
}
.form-warp-top{
	background-color: #fff;
	&>view{
		padding-right: 20px;
		height: 98px;
		display: flex;
		border-bottom: 1px solid #f5f5f5;
		align-items: center;
		position: relative;
	}
	&>view:first-child,&>view:last-child{
		border-bottom: 0;
	}
	image{
		max-width: 44px;
		max-height: 44px;
	}
	button{
		position: absolute;
		height: 62px;
		// background: #3491FA;
		line-height: 42px;
		border-radius: 4px 4px 4px 4px;
	}
	.mini-btn{
		right: 20px;
	}
	.mini-btn1{
		right: 184px;
	}
}
.text-type{
		width: 204px;
		margin-right: 54px;
		font-size: 34px;
		font-family: $font-family;
		font-weight: bold;
		color: #333333;
		padding: 25px 20px 25px 30px;
	}
	.text-value{
		width: 100%;
		flex: 1;
		font-weight: 400;
		
	}
.mini-btn{
	padding: 10px 42px;
	// width: 60px;
	height: 42px;
	font-size: 30px;
	font-family: $font-family;
	font-weight: 500;
	color: #FFFFFF;
	line-height:22px;
}
.form-warp-bottom{
	margin-top: 20px;
	background-color: #FFFFFF;
	padding: 32px 20px 32px 0px;
	display: flex;
	align-items: center;
	justify-content: space-between;
	position: relative;
	button{
		position: absolute;
		right: 20px;
		height: 62px;
		// background: #3491FA;
		line-height: 42px;
		border-radius: 4px 4px 4px 4px;
	}
}
</style>
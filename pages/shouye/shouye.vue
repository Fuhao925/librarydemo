<template>
	<view>
		<text class="username" v-model="username">姓名：{{username}}</text><br />
		<text class="idcard" v-model="idcard">学号：{{idcard}}</text>
		<uv-image class="usericon" src="../../static/img/user.png" width="80px" height="80px" shape="circle"></uv-image>
		<view class="d-flex just-content-center border-base "
			style="height:220rpx;width:90%;border-radius: 25rpx;margin-top:-50rpx">
		</view>
		<uv-button class="yuyue" type="primary" text="我要预约" icon="../../static/img/yuyue.png"></uv-button>
		<uv-button class="saoma" type="primary" text="扫码就坐" icon="../../static/img/saoma.png"></uv-button>
		<view class="bg">
			<image src="../../static/img/xuexi.png"></image>
		</view>
		<text class="text">你还没有预约记录!</text>
	</view>

</template>

<script>
	export default {
		data() {
			return {
				username: '222222',
				idcard: '123456'
			}
		},
		methods: {

		}
	}
</script>

<style>
	.bg {
		//背景图片
	}

	.text {
		position: absolute;
		text-align: center;
	}
	.usericon{
		position: absolute;
		right: 40px;
		top: 10px;
	}
	.username{
		position: absolute;
		left: 40px;
		top: 30px;
	}
	.idcard{
		position: absolute;
		left: 40px;
		top: 50px;
	}
</style>
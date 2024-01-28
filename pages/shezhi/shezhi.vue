<template>
	<view>
		<h1 class="h1">系统设置</h1>
		<uv-cell-group>
				<uv-cell title="修改密码" isLink url=""></uv-cell>
				<uv-cell title="投诉空座位" isLink url=""></uv-cell>
			</uv-cell-group>
		<div class="tuichu">
			<uv-button class="tuichu" type="error" size="large" text="退出登录"></uv-button>
		</div>
		
	</view>
	
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.h1 {
		color: white;
		background-color: cornflowerblue;
		text-align: center;
		margin: auto;
		height: 40px;
		width: 100%;
	}
	.tuichu{
		padding-top: 250px;
	}
</style>

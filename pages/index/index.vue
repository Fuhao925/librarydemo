<template>
	<view class="login">

		<h1 class="h1">用户登录</h1>


		<!-- <label for="school" class="selectschool">选择学校：</label>
		<select v-model="selectedSchool" @change="changeSchool">
			<option v-for="(school, index) in schools" :key="index" :value="school.id">{{ school.name }}</option>
		</select> -->
		
		
		<view class="login-content">
			<view class="login-username">
				<i class="el-icon-user"></i>
				<input type="text" placeholder="请输入账号" v-model="username">
			</view>
			<view class="login-password">
				<i class="el-icon-password"></i>
				<input type="password" name="" id="" placeholder="请输入密码" v-model="password">
			</view>
		</view>
		<view class="button"><button @click="onsubmit">登录</button></view>
	</view>
	</view>
</template>

<script>
	import {
		mapMutations
	} from 'vuex';
	export default {
		data() {
			return {
				selectedSchool: null,
				username: '',
				password: '',
				schools: [{
						id: 1,
						name: '汉江师范学院',
						accounts: ['userA1', 'userA2']
					},
					{
						id: 2,
						name: '湖北医药学院',
						accounts: ['userB1', 'userB2']
					},
					// Add more schools as needed
				]
			};
		},
		methods: {
			changeSchool() {
				// 在这里可以根据选择的学校更新其他相关的数据
			},
			login() {
				// 在这里可以添加登录逻辑，验证账号密码等
				if (this.selectedSchool !== null && this.username !== '' && this.password !== '') {
					const selectedSchoolObj = this.schools.find(school => school.id === this.selectedSchool);
					if (selectedSchoolObj && selectedSchoolObj.accounts.includes(this.username)) {
						// 登录成功的处理，可以跳转页面或执行其他操作
						console.log('登录成功');
					} else {
						console.log('登录失败：无效的账号或密码');
					}
				} else {
					console.log('请填写完整信息');
				}
			}
		}
	};
</script>

<style lang="less">
	.login {
		// background-image: linear-gradient(120deg, #00aaff, #55aaff);
		background-color: #fff;
		width: 100%;
		background-position: center;
		background-size: cover;
		// background-color: #464646;
		margin: 0px;
		background-size: 100% 100%;
		background-attachment: fixed;
		height: 1535rpx;
		opacity: 0.8;

		.login-title {
			padding-top: 150rpx;
			display: flex;
			justify-content: flex-start;
			margin-left: 50rpx;
			font-weight: 700;
			font-size: 40rpx;
			color: #55aaff;
			letter-spacing: 5rpx;
			margin-bottom: 50rpx;
		}

		.login-content {
			.login-username {
				display: flex;
				align-items: center;
				margin: 0 50rpx;
				border-bottom: 1rpx solid gainsboro;

				input {
					padding: 10rpx;
					height: 60rpx;
					width: 80%;
				}

				i {
					color: #55aaff;
					padding-right: 20rpx;
					font-size: 50rpx;
				}
			}

			.login-password {
				display: flex;
				align-items: center;
				margin: 0 50rpx;
				border-bottom: 1rpx solid gainsboro;
				margin-top: 50rpx;

				input {
					padding: 10rpx;
					height: 60rpx;
					width: 80%;
				}

				i {
					color: #55aaff;
					padding-right: 20rpx;
					font-size: 50rpx;
				}
			}
		}

		.button {
			margin-top: 120rpx;

			button {
				background-color: #55aaff;
				width: 90%;
				height: 85rpx;
				text-align: center;
				line-height: 85rpx;
				color: #fff;
			}
		}

		.h1 {
			color: white;
			background-color: cornflowerblue;
			text-align: center;
			margin: auto;
			height: 40px;
			width: 100%;
		}
	}

	.el-icon-user {
		background: url(../../static/img/user.png) no-repeat right;
		display: inline-block;
		background-position: 0px 0px;
		width: 40px;
		height: 35px;
	}

	.el-icon-password {
		background: url(../../static/img/password.png) no-repeat right;
		display: inline-block;
		background-position: 0px 0px;
		width: 40px;
		height: 35px;
	}
</style>
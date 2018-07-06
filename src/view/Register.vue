<template>
	<div style="margin: auto; width: 50%">
			<p style="font-size: 30px;">用户注册</p>
			姓&nbsp;&nbsp;&nbsp;名&nbsp; <el-input v-model="name" placeholder="请输入姓名" style="width: 30%"></el-input><br><br>
			用户名&nbsp; <el-input v-model="username" placeholder="请输入用户名" style="width: 30%"></el-input><br><br>
			手机号&nbsp; <el-input v-model="phone" placeholder="请输入手机号" style="width: 30%"></el-input><br><br>
			密&nbsp;&nbsp;&nbsp;码&nbsp; <el-input v-model="password" placeholder="请输入密码" style="width: 30%"></el-input><br><br>
			<el-button type="primary" round @click="register">注册</el-button>
			<el-button type="primary" round @click="doLogin">返回登录</el-button>
		</div>
</template>

<script type="text/javascript">
	export default{
		
		data() {
			return {
				name : '',
				username : '',
				phone : '',
				password : ''
			}
		},
		methods: {
			doLogin(){
				this.$router.push({path:'/login'})
			},
			register(){
				this.$axios({
				  method: 'post',
				  url: 'http://localhost:8080/register',
				  data: {
					  "name": this.name,
					  "password": this.password,
					  "phone": this.phone,
					  "username": this.username
					}
				}).then(response => {
					if (response.data.code == '0000') {
						 this.$message.success(response.data.msg);
						 this.$router.push({path:'/index'})
					} else if (response.data.code == '0001') {
						 this.$message.error(response.data.msg);
					} else {
						this.$message.error(response.data.msg);
					}
				}).catch(response => {
					console.log(response);
				});
			}
		}
	}
</script>

<style type="text/css">
	
</style>
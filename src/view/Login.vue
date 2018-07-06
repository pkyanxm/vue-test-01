<template>
	<div>
		<div style="margin: auto; width: 50%">
			<p style="font-size: 30px;">用户登陆</p>
			手机号&nbsp; <el-input v-model="phone" placeholder="请输入手机号" style="width: 30%"></el-input><br><br>
			密&nbsp;&nbsp;&nbsp;码&nbsp; <el-input v-model="password" placeholder="请输入密码" style="width: 30%"></el-input><br><br>
			<el-button type="primary" round @click="login">登陆</el-button>
			<el-button type="primary" round @click="register">注册</el-button>
		</div>
		
	</div>
</template>

<script type="text/javascript">
	export default{
		data() {
			return {
				phone : '',
				password : ''
			}
			
		},
		methods: {
			login(){
				this.$axios.get('http://localhost:8080/login?phone=' + this.phone + '&password=' + this.password).then(response => {
					if (response.data.code == '0001') {
						 this.$message.error(response.data.msg);
					} else if (response.data.code == '0002') {
						 this.$message.success(response.data.msg);
						 this.$router.push({path:'/index'})
					} else if (response.data.code == '0003') {
						 this.$message.error(response.data.msg);
					} else {
						this.$message.error(response.data.msg);
					}
				})
			},
			register(){
				this.$router.push({path:'/register'})
			}
		}
	}
</script>

<style type="text/css">
	
</style>
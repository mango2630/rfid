<template>
	<view class="container">
		<p>欢迎登陆</p>
		<view class="login" ref="login">
			<text class="us">Username</text>
			<input type="text" value="username" ref="username" v-model="username" />
			<text class="ps">Password</text>
			<input type="password" value="password" ref="password" v-model="password"/>
		</view>
		
		<button class="butLogin" type="default" @click="submit">账号密码登录</button>
		<navigator url="../faceid/FaceIdLog">
			<button class="butFace" type="default">人脸识别登录</button>
		</navigator>
	</view>
	
</template>

<script>
	export default{
		name:"Login",
		data(){
			return{
				username : null,
				password : null
			}
		},
		computed:{
			login(){
				return{
					stuNumber : this.username,
					password : this.password
				}
			}
		},
		methods:{
			goStorage(){
				uni.switchTab({
					url:"../storage/storage"
				})
			},
			submit(){
				uni.request({
					url:  "http://111.229.238.150:8188/login/check",
					method:'POST',
					data:this.login,
					
					// success:function(res){
						// console.log(res);
						
					// }
				}).then(res=>{
					// console.log(res);
					// console.log(res.data.message)
					if(res[1].data.message === true){
						// alert("注册成功");
						
						uni.switchTab({
							url:"../storage/Storage"
						})
					}
				}).catch(err=>{
					console.log(err);
				})
			}
		}
		
	}
</script>

<style scoped>
	@import url("../../static/login/style.css");
	
</style>
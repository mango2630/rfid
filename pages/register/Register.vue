<template>
	<view>
		<view class="register" ref="register">
			<text>username</text>
			<input type="text" value="username" ref="username" v-model="username"/>
			<text>email</text>
			<input type="text" value="email" ref="email"v-model="email"/>
			<text>password</text>
			<input type="text" value="password" ref="password" v-model="password"/>
			<navigator url="../faceid/FaceIdReg">
				<button type="default">人脸识别信息录入</button>
			</navigator>
		</view>
		<button type="default" @click="submit">注册</button>
		邮箱验证暂搁置
	</view>
</template>

<script>
	export default{
		name:'Register',
		data(){
			return{
				username:null,
				email:null,
				password:null
			}
		},
		methods:{
			submit(){
				console.log("register");
				uni.request({
					url:"http://111.229.238.150:8188/register/verifyuser",
					method:'POST',
					data:this.register
				}).then(res=>{
					console.log(res);
					console.log(this.register);
					
					if(res.data === "success"){
						alert("注册成功");
					}
				}).catch(err=>{
					console.log(err);
				})
			}
		},
		computed:{
			register(){
				return {
					// change
					stuNumber : this.username,
					mailbox : this.email,
					password : this.password
				}
			}
		}
	}
</script>

<style>
	input{
		border-bottom: 1px solid black;
		width: 500rpx;
	}
</style>

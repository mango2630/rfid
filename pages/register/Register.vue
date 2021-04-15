<template>
	<view class="container">
		<p>欢迎注册</p>
		<view class="register" ref="register">
			<text>username</text>
			<input type="text" value="username" ref="username" v-model="username"/>
			<text>email</text>
			<input type="text" id="bugMaker" value="email" ref="email"v-model="email" />
			<text>password</text>
			<input type="text" value="password" ref="password" v-model="password"/>
			
		</view>
		
		<navigator url="../faceid/FaceIdReg">
			<button class="butFace" type="default">人脸识别信息录入</button>
		</navigator>
		<button class="butReg" type="default" @click="submit">注册</button>
		<!-- 邮箱验证暂搁置 -->
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
				const reg = /^([a-zA-Z]|[0-9])(\w|\-)+@[a-zA-Z0-9]+\.([a-zA-Z]{2,4})$/;
				if (reg.test(this.email)) {
					uni.request({
						url:"http://111.229.238.150:8188/register/verifyuser",
						method:'POST',
						data:this.register
					}).then(res=>{
						console.log(res);
						console.log(this.register);
						uni.showToast({
							title:"注册成功",
							duration:500
						})
						if(res.data === "success"){
							// alert("注册成功");
							uni.showToast({
								title:"注册成功",
								duration:500
							})
						}
					}).catch(err=>{
						console.log(err);
					})
				} else {
					// alert("傻逼");
					uni.showModal({
					    title: '提示',
					    content: '邮箱格式输入错误',
					    success: function (res) {
					        if (res.confirm) {
					            console.log('用户点击确定');
					        } else if (res.cancel) {
					            console.log('用户点击取消');
					        }
					    }
					});
				}
				console.log("register");
				
			},
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

<style scoped>
	
	@import url("../../static/register/style.css");
	.changeEmail {
		border-bottom: 10px solid #000 !important;
	}
	
</style>

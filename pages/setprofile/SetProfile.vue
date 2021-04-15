<template>
	<view class="container">
		<view class="img">
			<span>头像</span>
			<image src="../../static/profile/img/logo.png" mode=""></image>
			<text> > </text>
		</view>
		<view @click="skip(1)" class="nickname">
			<span>昵称</span>
			<span class="nick">mango</span>
			<text> > </text>
		</view>
		<view @click="skip(2)" class="positon">
			<span>职位</span>
			<span class="job">董事长</span>
			<text> > </text>
		</view>
		<view @click="skip(3)" class="phone">
			<span>手机号</span>
			<p>13572797966</p>
			<text> > </text>
		</view>
	</view>
</template>

<script>
	export default{
		name : "SetProfile",
		data(){
			return{
				
			}
		},
		methods:{
			skip(value){
				switch(value){
					case 1:
						uni.navigateTo({
							url: "./ModifyNickName"
						});
						break;
					case 2:
						uni.navigateTo({
							url:"./ModifyPosition"
						});
						break;
					case 3:
						uni.navigateTo({
							url : "./ModifyPhone"
						})
						break;
					default:
						console.log("err");
						break;
				}
			}
		}
	}
</script>

<style scoped>
	@import url("../../static/setprofile/style.css");
</style>
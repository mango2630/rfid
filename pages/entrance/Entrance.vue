<template>
	<view class="container">
		<p class="p1">
			欢迎使用
		</p>
		
		<p class="p2">
			RFID管理设备
		</p>
		
		<p class="p3">Please select login or register</p>
		<navigator url="../login/Login" >
			<button type="default" class="login">登录</button>
		</navigator>
		
		<navigator url="../register/Register">
			<button type="default" class="register">注册</button>
		</navigator>
	</view>
</template>

<script>
	export default{
		
	}
</script>

<style>
	@import url("../../static/entrance/style.css");
</style>
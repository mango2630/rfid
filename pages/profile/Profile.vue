<template>
	<view class="body">
		
		<view class="img">
			<image src="../../static/logo.png" mode=""></image>
		</view>
		
		<text>nickname: mango</text><br>
		<text>username: 19407010204</text><br>
		<text>性别：女</text><br>
		<text>个性标签</text>
		
		<navigator url="../setprofile/SetProfile">
			<button type="default" class="mineButton">个人信息设置</button>
		</navigator>
		
		<navigator url="../entrance/Entrance" open-type="redirect" >
			<button type="default" class="balckButton">退出登录</button>
		</navigator>
	</view>
</template>

<style>
	@import url("../../static/profile/css/style.css");
	
</style>
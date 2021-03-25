<template>
	<view>
		
		<view class="img">
			<image src="../../static/logo.png" mode=""></image>
		</view>
		
		<text>nickname: mango</text><br>
		<text>username: 19407010204</text><br>
		<text>性别：女</text><br>
		<text>个性标签</text>
		
		<navigator url="../setprofile/SetProfile">
			<button type="default">个人信息设置</button>
		</navigator>
		
		<navigator url="../entrance/Entrance">
			<button type="default">退出登录</button>
		</navigator>
	</view>
</template>

<style>
	image{
		width: 50rpx;
		height: 50rpx;
	}
</style>
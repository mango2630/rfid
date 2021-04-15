<template>
	<!-- start:header -->
	<view class="header">
		<!-- search bar -->
		<view class="search">
			<input type="text" value="value" />
			<button type="default">搜索</button>
		</view>
	</view>
	<!-- end:header -->
</template>

<script>
	export default {
		name : 'SearchBar',
	}
</script>

<style>
.header{
	width: 100%;
	height: 80rpx;
	position: relative;
	/* left: 0;
	top: 0; */
	/* margin-bottom: 40rpx; */

}

.header .search{
	width: 97%;
	height: 90%;
	border: 2px solid #1296db;
	border-radius: 100rpx;
	position: relative;
	left: 10rpx;
	right: 10rpx;
	top: 0;
}
.header .search input{
	width: 65%;
	height: 100%;
	position: absolute;
	left: 40rpx;
}

.header .search button{
	width: 20%;
	height: 85%;
	border-radius: 100rpx;
	line-height: 65rpx;
	position: absolute;
	right: 10rpx;
	top: 5rpx;
	background-color: #99A9BF;
}

</style>

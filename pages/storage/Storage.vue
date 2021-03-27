<template>
	<view>
		<!-- start:header -->
		<view class="header">
			<!-- search bar -->
			<view class="search">
				<input type="text" value="value" />
				<button type="default">搜索</button>
			</view>
		</view>
		<!-- end:header -->
		
		<!-- start: slider -->
		<view class="slider">
			<swiper class="swiper" :indicator-dots="true" :autoplay="true" :interval="3000" 
			:duration="1000" :circular="true">
				<swiper-item  v-for="(item, index) in arrSlider" :key="index">
					<image :src="item"></image>
				</swiper-item>
			</swiper>
		</view>
		<!-- end:slider -->
		
		
		<!-- 瀑布流效果？？？？？ 2个月没写，人傻了，居然不会写了 -->
		<!-- start: display equipment -->
		<view class="display">
			<view class="equip1">
				<image src="../../static/logo.png" mode=""></image>
				<text class="name">deviceName</text><br>
				<text class="num">当前数量</text><br>
				<text class="">总数量</text><br>
			</view>
			<view class="equip2">
				<image src="../../static/logo.png" mode=""></image>
				<text class="name">deviceName</text><br>
				<text class="num">当前数量</text><br>
				<text class="">总数量</text><br>
			</view>
		</view>
		<!-- end: display equipment -->
		
		
		
		
		<navigator url="../borrowrequest/ReqBor">
			<!-- <button type="default">借用</button> -->
			
			<!-- start : check the progress -->
			<view class="checkbox">
				<image src="../../static/request/request.png" mode=""></image>
			</view>
			<!-- end : check the progress -->
		</navigator>	
		
	</view>
</template>

<script>
	
	
	export default{
		data(){
			return{
				arrSlider : ["../../static/slider/1.jpg", "../../static/slider/2.jpg", 
				"../../static/slider/3.jpg", "../../static/slider/4.jpg"],
				
			}
		},
		methods:{
			
		},
		mounted() {
			console.log("mounter");
			
			// equip
			uni.request({
				url: "http://api.bdsplugins.cn/api/equipment",
				method:'GET',
				success:(res)=>{
					console.log(res.data);
					/*
					0 ： 借出
					1 ： 在仓库
					2 ： 损坏或丢失
					*/
				}
			})
			
			// count
			uni.request({
				url: 'http://api.bdsplugins.cn/api/deviceCount',
				method:'GET',
				success : (res)=>{
					console.log(res.data);
				}
			})
		},
		components:{
			
		}
	}
</script>

<style scoped>
	@import url("../../static/storage/style.css");
</style>
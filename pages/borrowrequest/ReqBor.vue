<template>
	<view class="container">
		<ul class="content">
			<li v-for="(item,index) in listArr">
				<!-- &#xe64b; -->
				<span v-if="item.flag==false" class="iconfont">&#xe608;</span>
				
				<span v-if="item.flag==true" class="iconfont">&#xe64b;</span>			
			
				<text>
					<text>{{item.tag}}</text>
					<text>2020-02-03 18:32</text>
				</text>
			</li>
			
		</ul>
		
	</view>

</template>

<script>

	export default{
		name : 'ReqBor',
		data(){
			return{
				listArr : [
					{tag:'发送借用消息', flag:true},
					{tag:'接单通知',flag:false},
					{tag:'向管理员发送转借请求', flag:false},
					{tag:'管理员审核',flag:false},
					{tag:'审核通过',flag:false}
				],
				defaultLogo : '&#xe608;',
				changeLog : '&#xe64b;',
				flag : false
			}
		},
		components:{
		}
	}
	
</script>

<style>
	@import url("../../static/request/font_3k63jc5tlyz/iconfont.css");
	@import url("../../static/request/css/style.css");
</style>
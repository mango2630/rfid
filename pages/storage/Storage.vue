<template>
	<view>

		1.搜索框（可根据设备名称、型号等来查找从仓库要借用的设备<br>
			借用（按钮）-> 向管理员发借用请求（表单）-> 审批进度（分n个阶段）<br>
			ps : 右上角小logo，点进去为自己当前所借用的设备的进度<br>
		2.设备slider	<br>
		3.设备陈列<br>
			陈列设备的信息：<br>
			1. 设备名称<br>
			2. 设备型号<br>
			3. 设备...<br>
			4. 数量...<br>
		<navigator url="../borrowrequest/ReqBor">
			<button type="default">借用</button>
		</navigator>	
		
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			
		}
	}
</script>
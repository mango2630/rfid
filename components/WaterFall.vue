<template>
	<view class="waterfall-width-column">
		<view class="image-box" v-for="img in imgList" :key="img">
			<image src="img" mode=""></image>
		</view>
	</view>
</template>

<script>
	export default{
		methods: {
		     //计算图片列数
		    getColNumbers() {
		      let clientWidth = this.$refs.waterfall.clientWidth
		      this.colNumbers = Math.floor(clientWidth / this.colWidth)
		    },
		    //读取图片
		    loadImage() {
		      this.getColNumbers()
		      for (let i = 0; i < 17; i++) {
		        let colIndex = i % this.colNumbers
		        let url = require(`@/assets/images/${i}.jpg`)
		        if (this.imgList[colIndex]) {
		          this.imgList[colIndex].push(url)
		        } else {
		          this.$set(this.imgList, colIndex, [url])
		        }
		      }
		    },
		  }
	}
</script>

<style lang="scss" scoped>
	.waterfall-width-column {
	  column-count: 3;
	  column-gap: 10px;
	  .image-box {
	    img {
	      display: block;
	      width: 100%;
	    }
	  }
	}
	
	
</style>
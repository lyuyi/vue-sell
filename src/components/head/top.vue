<template>
	<div class="head">
		<!-- 头部内容区 -->
		<div class="content-wrapper">
			<div class="avatar">
				<img  width="64" height="64" :src="seller.avatar">
			</div>
			<div class="content">
				<div class="title">
					<span class="brand"></span>
					<span class="name">{{seller.name}}</span>
				</div>
				<div class="description">
					{{seller.description}}/{{seller.deliveryTime}}分钟送达
				</div>
				<div class="support" v-if="seller.support"><!--如果不判断会报错：'0' of undefined，因为初始化seller时是个空对象，将其传给.header就会报错-->
					<span class="icon"></span>
					<span class="text">{{seller.supports[0].description}}</span>
				</div>
			</div>
		</div>
		<!-- 公告区 -->
		<div class="bulletin-wrapper">
			
		</div>
	</div>
</template>
<script type="text/ecmascript-6">
	export default {
	  props: {// props接收传App.vue过来的seller
      seller: {
        type: Object
      }
    }
	};
</script>
<style lang="stylus" rel="stylesheet/stylus">
	@import "../../common/stylus/mixin";、
	.head
	  color: #fff
	  background: #000
	  .content-wrapper
	    padding: 24px 12px 18px 24px
	    font-size: 0//消除之间缝隙
	    .avatar
	      display: inline-block
	    .content
	      display: inline-block
	      font-size: 14px
	      margin-left: 16px
</style>
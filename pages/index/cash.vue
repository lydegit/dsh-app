<template>
	<view style="margin: 10px;">
		<view style="padding-top: 20px;">
			<input class="inputStyle" maxlength="10" style="" name ="bookName" focus placeholder="搜索书名" />
		</view>
		<view>
			<scroll-view scroll-x="true" class="scrollStyle" >
				<view id="demo1" class="scrollStyle_item">小说文学</view>
				<view id="demo2" class="scrollStyle_item">历史传记</view>
				<view id="demo3" class="scrollStyle_item">人文社科</view>
				<view id="demo3" class="scrollStyle_item">人文社科</view>
				<view id="demo3" class="scrollStyle_item">人文社科</view>
				<view id="demo3" class="scrollStyle_item">人文end</view>
			</scroll-view>
		</view>
		<view>
			<view class="listStyle">
				<view class="listStyle_item_left">文字</view>
				<view class="listStyle_item_right">
					<view style="padding-top:7px;font-size: 17px;font-weight :550;">失落的卫星</view>
					<view style="padding-top:5px;font-size: 14px;color:#BCBEC2;">作者：刘子超</view>
					<view style="padding-top:15px;font-size: 17px;width: 90%;">
						<label style="">￥19.90</label>
						<label style="float: right;">￥19.90</label>
					</view>
				</view>
			</view>
			<view class="listStyle">
				<view class="listStyle_item_left">文字</view>
				<view class="listStyle_item_right">
					<view style="padding-top:7px;font-size: 17px;font-weight :550;">失落的卫星</view>
					<view style="padding-top:5px;font-size: 14px;color:#BCBEC2;">作者：刘子超</view>
					<view style="padding-top:15px;font-size: 17px;width: 90%;">
						<label style="">￥19.90</label>
						<label style="float: right;">￥19.90</label>
					</view>
				</view>
			</view>
			<view class="listStyle">
				<view class="listStyle_item_left">文字</view>
				<view class="listStyle_item_right">
					<view style="padding-top:7px;font-size: 17px;font-weight :550;">失落的卫星</view>
					<view style="padding-top:5px;font-size: 14px;color:#BCBEC2;">作者：刘子超</view>
					<view style="padding-top:15px;font-size: 17px;width: 90%;">
						<label style="">￥19.90</label>
						<label style="float: right;">￥19.90</label>
					</view>
				</view>
			</view>
			<view class="listStyle">
				<view class="listStyle_item_left">文字</view>
				<view class="listStyle_item_right">
					<view style="padding-top:7px;font-size: 17px;font-weight :550;">失落的卫星</view>
					<view style="padding-top:5px;font-size: 14px;color:#BCBEC2;">作者：刘子超</view>
					<view style="padding-top:15px;font-size: 17px;width: 90%;">
						<label style="">￥19.90</label>
						<label style="float: right;">￥19.90</label>
					</view>
				</view>
			</view>
			<view class="listStyle" >
				<view class="listStyle_item_left">文字</view>
				<view class="listStyle_item_right">
					<view style="padding-top:7px;font-size: 17px;font-weight :550;">失落的卫星</view>
					<view style="padding-top:5px;font-size: 14px;color:#BCBEC2;">作者：刘子超</view>
					<view style="padding-top:15px;font-size: 17px;width: 90%;">
						<label style="">￥19.90</label>
						<label style="float: right;">￥19.90</label>
					</view>
				</view>
			</view>
			<view style="padding-bottom: 35px;"></view>
		</view>
		<view style="width: 100%;display: flex;background-color: #808080;height: 35px;position: fixed;bottom: 0;left: 0;z-index: 500;">
			<view style="width: 50%;background-color:#FFFFFF;">合计</view>
			<view style="width: 50%;float: left;background-color: #007AFF;">购买</view>
		</view>
		 
	</view>
	
</template>

<script>
	export default {
	    data() {
	        return {
	            scrollTop: 0,
	            old: {
	                scrollTop: 0
	            }
	        }
	    },
	    methods: {
			
	    }    
	}
</script>

<style>
	page{
			background-color: #F5F5F5;
	}
	.inputStyle {
		text-align: center;/*主要就是这个，下面的都是样式*/
		width: 70%;
		height: 2.5rem;
		border: 1px solid #d8e1f4; 
		font-size: 14px;
		line-height: 48px;
		border-radius: 25px;
		margin: 0 auto;
		outline: none　　/*outline设置为空，可以达到输入框激活状态时不出现方框*/
	}
	.scrollStyle {
		padding-top: 30px;
		width: 100%;
		height: 60upx;
		display: flex;
		flex-direction: row;
		white-space: nowrap;
	}
	.scrollStyle_item {
		text-align: left;
		overflow: hidden;
		background-color: #efefef;
		margin: 2upx;
		width: 170upx;
		height: 50upx;
		display: inline-block;
		color:#808080;
	}
	.listStyle {
		display: flex;
	    width: 100%;
		height: 100px;
		padding-top: 10px;
	}	
	.listStyle_item_left {
	    width: 30%;
		height: 100px;
		line-height: 100px;
		background-color: #eaeaea;
		text-align: center;
		margin: 0 auto;
	}
	.listStyle_item_right {
		width: 70%;
		background-color: #FFFFFF;
	}
	.listStyle_item_right view {
		padding-left: 10px;
	}
</style>

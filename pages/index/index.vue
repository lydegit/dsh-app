<template>
	<view class="container" >
		  <form @submit="formSubmit">
			<view class="item">
			  <view class="title">部门</view>
			  <input class="uni-input" maxlength="10" name ="bm" focus placeholder="请输入部门" />
			</view>
			<view class="item">
			  <view class="title">岗位</view>
			  <input class="uni-input" maxlength="10" name ="gw" placeholder="请输入岗位" />
			</view>
			<view class="item">
				<view class="title">手机号</view>
				<input class="uni-input" maxlength="11" type ="number" name="phone" placeholder="请输入手机号" />
			</view>
			<view class="uni-btn-v"style="padding-top: 20%;">
				<button form-type="submit"  type="primary">确定</button>
			</view>
		 </form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				href: 'https://uniapp.dcloud.io/component/README?id=uniui',
				openid: ""
			} 
		},
		onLoad: function (option) { //option为object类型，会序列化上个页面传递的参数
		    console.log(option); //打印出上个页面传递的参数。
			let routes = getCurrentPages(); // 获取当前打开过的页面路由数组
			let curRoute = routes[routes.length - 1].route 
			console.log("curRoute=="+curRoute);
			var openidStr = option.openid
			this.openid = openidStr;
			if(openidStr == "" || openidStr == null){
				uni.navigateTo({
						url: "http://wechat.clianmeng.cn/mp/auth/openid?appid=wxd141be9c6628d5ab&ref="+curRoute,
				});
			}else{
				 uni.request({
				    url: 'http://localhost:8156/dsh/findUserByOpenid', //仅为示例，并非真实接口地址。
					method: 'POST',
				    data: {
						openid: this.openid
				    },
				    header: {
				        'custom-header': 'hello' //自定义请求头信息
				    },
				    success: (res) => {
				        console.log(res.data);
						var dataBack = res.data
						if(dataBack.status == "success"){
							uni.redirectTo({
							    url: 'cash?userId='+dataBack.data.id
							});
						}
				    }
				}); 
			} 
		},
		methods: {
			formSubmit: function(e) {
				console.log('form发生了submit事件，携带数据为：' + JSON.stringify(e.detail.value))
				console.log(e.detail.value.phone)
				var formdata = e.detail.value
				uni.request({
				    url: 'http://localhost:8156/dsh/addUser', //仅为示例，并非真实接口地址。
					method: 'POST',
				    data: {
						bm: formdata.bm,
						gw: formdata.gw,
						phone: formdata.phone,
						openid: this.openid
				    },
				    header: {
				        'custom-header': 'hello' //自定义请求头信息
				    },
				    success: (res) => {
				        console.log(res.data);
				        this.text = 'request success';
				    }
				});
			},
			
		}
	}
	
</script>

<style>
	page{
			background-color: #F5F5F5;
	}
	.container {
		padding: 20px;
		font-size: 14px;
		line-height: 24px;
	}
	.item{
	         display: flex;
	         justify-content: space-between;
	         align-items:center;
			 padding-top: 40px;
	 }
	 .item view{
	          width: 20%;
			  font-size: 20px;
			  
	  }
	  .item input{
		  width: 80%;
	  }
</style>

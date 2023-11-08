<template>
	<view class="content" :style="[{backgroundColor: backgroundColor}]">
		<view class="title_wapper" :style="[{filter: filter}]">
			<navigator url="../../index/index">
				<p>智慧靶感知系统</p>
			</navigator>
		</view>
		
		<form @submit="login" @reset="">
			<view class="middle_wapper" :style="[{filter: filter}]">
				<!-- logo -->
				<image src="../../../static/logo.png" mode=""></image>
				
				<picker @change="buDui" :range="buDuiArray" class="single_box">
					<label style="margin-top: 25upx;margin-left: 60upx;color: #555555;display: flex;">{{nowBuDui}}</label>
				</picker>
				<picker @change="name" :range="nameArray" class="single_box">
					<label style="margin-top: 25upx;margin-left: 60upx;color: #555555;display: flex;">{{nowName}}</label>
				</picker>
		
				<button form-type="" class="btn" style="margin-top: 40upx;" @click="login">登录</button>
				<button @click="openPop" class="btn">新增指导员</button>
			</view>
		</form>
		
		<!-- 弹出层 -->
		<form @submit="addSoldier" @reset="">
			<view class="pop_wapper" :style="[{display: display}]">
				<view class="pop_top">
					<p>新增指导员</p>
				</view>
				<input name="club" type="text" placeholder="请填写所在部队(必填)" style="margin-top: 60upx;"/>
				<input name="leaderName" type="text" placeholder="请填写指导员姓名(必填)" />
				<input name="Telephone" type="number" placeholder="请填写联系方式(选填)" />
				<view style="display: flex; margin-left: 8%;">
					<button @click="addSoldier" class="btn2">确定</button>
					<button @click="closePop" class="btn2" style="background-color: #23A6DD;">取消</button>
				</view>
			</view>
		</form>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				buDuiArray:['一号部队','二号部队','三号部队'],
				buDuiIndex:0,
				nowBuDui:"--请选择指导员所在部队",
				nameArray:['张三','李四','王麻子'],
				nameIndex:0,
				nowName:"--请选择指导员姓名",
				display:'none',
				filter:'opacity(1)',
				backgroundColor:'#FFFFFF',
			}
		},
		methods:{
			buDui(e) {
			    this.buDuiIndex = e.target.value;
			    this.nowBuDui=this.buDuiArray[this.buDuiIndex]
			},
			name(e) {
				this.nameIndex = e.target.value;
				this.nowName=this.nameArray[this.nameIndex]
			},
			baWei(e){
				this.baWeiIndex = e.target.value;
				this.nowBaWei=this.baWeiArray[this.baWeiIndex]
			},
			// 登录
			login(){
				console.log("login")
				// 页面跳转
				uni.navigateTo({
					url:"../../leader/nowBawei/nowBawei"
				})
			},
			//打开弹出窗
			openPop(){
				this.display='block';
				this.filter = 'opacity(0.2)';
				this.backgroundColor='rgba(239, 239, 239, 0.8)';
			},
			// 添加士兵
			addSoldier(){
				console.log(11111)
				
				
				this.display='none';
				this.filter = 'opacity(1)';
				this.backgroundColor='#FFFFFF';
				
			},//取消
			closePop(){
				if(this.display=='block'){
					this.display='none';
					this.filter = 'opacity(1)';
					this.backgroundColor='#FFFFFF';
				}
			}
				
		}
	}
</script>

<style>
	@import url("leader_login.css");
</style>

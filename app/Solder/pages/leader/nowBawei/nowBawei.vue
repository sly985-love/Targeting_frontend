<template>
	<view class="page">
		<!-- 头部导航栏：吸顶 -->
		<view class="header" id="boxFixed" :class="{'is_fixed' : isFixed}">
			<navigator url="" style="border-bottom: #DD524D 8upx solid;color:#000000;">实时靶位</navigator>
			<navigator url="../BaweiLog/BaweiLog">实时记录</navigator>
			<navigator url="../BaweiTongJi/BaweiTongJi">实时统计</navigator>
			<navigator url="../leaderMe/leaderMe">我的</navigator>
		</view>
		
		<!-- 中部内容 -->
		<view class="middle page-block">
			<view class="middle_title">所 有 靶 位 情 况 实 时 展 示</view>
			<view class="middle_btn">
				<view :style="[{filter: filter}]" @click="begin">开始</view>
				<view style="background-color: #E43D33;" :style="[{filter: filter2}]" @click="end">结束</view>
			</view>
			<!-- 靶位内容 -->
			<view class="middle_content">
				<!-- 单个靶位 -->
				<view class="single_bawei">
					<!-- 浮动的战士+靶位信息 -->
					<view class="single_info">
						<p>战士:刘雨昕&nbsp;&nbsp;靶位:01</p>
					</view>
					<!-- 打靶实时虚拟图片 -->
					<image src="../../../static/leader/nowDaba.jpg" id="nowDaba"></image>
					<!-- 打靶结果 -->
					<view class="single_result">上靶 : 5次 &nbsp;&nbsp; 合计 : 16环</view>
				</view>
				
				<!-- 单个靶位 -->
				<view class="single_bawei">
					<!-- 浮动的战士+靶位信息 -->
					<view class="single_info">
						<p>战士:刘雨昕&nbsp;&nbsp;靶位:01</p>
					</view>
					<!-- 打靶实时虚拟图片 -->
					<image src="../../../static/leader/nowDaba.jpg" id="nowDaba"></image>
					<!-- 打靶结果 -->
					<view class="single_result">上靶 : 5次 &nbsp;&nbsp; 合计 : 16环</view>
				</view>
				
				<!-- 单个靶位 -->
				<view class="single_bawei">
					<!-- 浮动的战士+靶位信息 -->
					<view class="single_info">
						<p>战士:刘雨昕&nbsp;&nbsp;靶位:01</p>
					</view>
					<!-- 打靶实时虚拟图片 -->
					<image src="../../../static/leader/nowDaba.jpg" id="nowDaba"></image>
					<!-- 打靶结果 -->
					<view class="single_result">上靶 : 5次 &nbsp;&nbsp; 合计 : 16环</view>
				</view>
				
				<!-- 单个靶位 -->
				<view class="single_bawei">
					<!-- 浮动的战士+靶位信息 -->
					<view class="single_info">
						<p>战士:刘雨昕&nbsp;&nbsp;靶位:01</p>
					</view>
					<!-- 打靶实时虚拟图片 -->
					<image src="../../../static/leader/nowDaba.jpg" id="nowDaba"></image>
					<!-- 打靶结果 -->
					<view class="single_result">上靶 : 5次 &nbsp;&nbsp; 合计 : 16环</view>
				</view>
				
				<!-- 单个靶位 -->
				<view class="single_bawei">
					<!-- 浮动的战士+靶位信息 -->
					<view class="single_info">
						<p>战士:刘雨昕&nbsp;&nbsp;靶位:01</p>
					</view>
					<!-- 打靶实时虚拟图片 -->
					<image src="../../../static/leader/nowDaba.jpg" id="nowDaba"></image>
					<!-- 打靶结果 -->
					<view class="single_result">上靶 : 5次 &nbsp;&nbsp; 合计 : 16环</view>
				</view>
				
				<!-- 单个靶位 -->
				<view class="single_bawei">
					<!-- 浮动的战士+靶位信息 -->
					<view class="single_info">
						<p>战士:刘雨昕&nbsp;&nbsp;靶位:01</p>
					</view>
					<!-- 打靶实时虚拟图片 -->
					<image src="../../../static/leader/nowDaba.jpg" id="nowDaba"></image>
					<!-- 打靶结果 -->
					<view class="single_result">上靶 : 5次 &nbsp;&nbsp; 合计 : 16环</view>
				</view>
				
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return{
				isFixed: false,
				offsetTop: 0,
				filter:'opacity(0.5)',
				filter2:'opacity(0.5)',
			}
		},
		mounted() {
		    window.addEventListener('scroll', this.initHeight);
	        this.$nextTick(() => {
           //获取对象相对于版面或由 offsetTop 属性指定的父坐标的计算顶端位置 
			this.offsetTop = document.querySelector('#boxFixed').offsetTop;
		    })
		},
		methods: {
		    initHeight() {
				// 设置或获取位于对象最顶端和窗口中可见内容的最顶端之间的距离 (被卷曲的高度)
				var scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop
				//如果被卷曲的高度大于吸顶元素到顶端位置 的距离
				this.isFixed = scrollTop > this.offsetTop ? true : false;
		    },
			begin(){
				this.filter='opacity(1)';
				
			},
			end(){
				this.filter2='opacity(1)';
				
			}
			
			
			
		},
		//回调中移除监听
		destroyed() {
			window.removeEventListener('scroll', this.handleScroll)
		}
		
	}
</script>

<style>
	@import url("nowBawei");
</style>

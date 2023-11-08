<template>
	<view class="page">
		<!-- 头部导航栏：吸顶 -->
		<view class="header" id="boxFixed" :class="{'is_fixed' : isFixed}">
			<navigator url="../nowBawei/nowBawei">实时靶位</navigator>
			<navigator url="../BaweiLog/BaweiLog">实时记录</navigator>
			<navigator url="" style="border-bottom: #DD524D 8upx solid;color: #000000;">实时统计</navigator>
			<navigator url="../leaderMe/leaderMe">我的</navigator>
		</view>
		
		<!-- 中部内容 -->
		<view class="middle page-block">
			<view class="middle_title">所 有 靶 位 情 况 实 时 统 计</view>
			<view class="middle_btn">
				<view :style="[{filter: filter}]" @click="begin">开始</view>
				<view style="background-color: #E43D33;" :style="[{filter: filter2}]" @click="end">结束</view>
			</view>
			<!-- 实时统计内容 -->
			<view class="middle_content">
				<!-- 单个 -->
				<view class="middle_single" v-for="i in array">
					<view class="f_title">战士:刘雨昕 &nbsp;靶位:01</view>
					<!-- 表格 -->
					<view class="f_content">
						<view id="table_title">
							<p id="t_first">环数</p>
							<p id="t_second">共打中次数</p>
						</view>
						<view id="table_title">
							<p id="t_first">10环</p>
							<p id="t_second">1次</p>
						</view>
						<view id="table_title">
							<p id="t_first">9环</p>
							<p id="t_second">0次</p>
						</view>
						<view id="table_title">
							<p id="t_first">8环</p>
							<p id="t_second">2次</p>
						</view>
						<view id="table_title">
							<p id="t_first">7环</p>
							<p id="t_second">1次</p>
						</view>
						<view id="table_title">
							<p id="t_first">6环</p>
							<p id="t_second">1次</p>
						</view>
					</view>
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
				array:[1,2,3,4,5,6]
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
	@import url("BaweiTongji");
</style>

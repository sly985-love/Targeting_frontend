<template>
	<view class="page" style="background-color: white;display: flex;flex-direction: column;align-items: center;height: 1500upx;">
		<!-- 头部：title + 视频 + 信息按钮 -->
		<view class="top page-block">
			<view class="title">实 时 靶 面</view>
			<view class="video">   <!-- 实时打靶视频 -->
				<image src="../../../static/history/real_Daba.jpg" mode=""></image>
			</view>
			<view class="info">
				<view class="info_single">战士 : 刘雨昕</view>
				<view class="info_single" style="background-color: #fac858;">靶位 : 一号</view>
			</view>
		</view>
		
		<!-- 中部：成绩分析 -->
		<view class="middle page-block">
			<view class="m_single">
				<p style="font-size: 40upx;color: #000000;font-weight: 500;">4次</p>
				<p>上靶总计</p>
			</view>
			<view class="m_single"> 
				<p style="font-size: 40upx;color: #000000;font-weight: 500;">078环</p>
				<p>环数总计</p>
			</view>
		</view>
		
		<!-- 底部：每次上靶的具体成绩 -->
		<view class="footer">
			<view class="f_title">成 绩 详 情</view>
			<view class="f_content">
				<p>—第一次：9环</p>
				<p>—第二次：8环</p>
				<p>—第三次：7环</p>
				<p>—第四次：10环</p>
				<p>—第五次：6环</p>
			</view>
		</view>
	
		
	</view> 
</template>

<script>
	export default{
		data(){
			return{
				
				
			}
		},
		methods: {
		        
		}
	}
</script>

<style>
	@import url("watch");
</style>

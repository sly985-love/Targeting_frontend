<template>
	<view class="page">
		<!-- 头部标题 -->
	<!-- 	<view class="header">
			<p>历史打靶记录</p>
		</view> -->
	
		<!--轮播图 start-->
		<!--swiper轮播 ①indicator-dots：指示点；②autoplay：自动播放；-->
		<swiper :indicator-dots="true" :autoplay="true" class="hb">
			<swiper-item>
				<image src="../../../static/swapper/1.png" class="hb"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../../static/swapper/2.jpg" class="hb"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../../static/swapper/3.jpg" class="hb"></image>
			</swiper-item>
		</swiper>
		<!--轮播块 end-->
			
		<!-- 打靶成绩柱状图 + 打靶习惯 -->
		<view class="grade_wapper page-block">
			<!-- 标题 + 内容 -->
			<view class="title_wapper">
				<image src="../../../static/history/daba.png" id="smallIcon"></image>
				<p style="margin-left: 14upx;">近五次打靶成绩</p>
			</view>
			<view class="grade_content">
				<qiun-data-charts
				    type="column"
				    :chartData="chartData"
					background="none"
					style="margin-top: 20upx;"
				/>
			</view>
		</view>
		
		
		<!-- 统计结论 -->
		<view class="fenxi page-block">
			<!-- 标题 + 内容 -->
			<view class="title_wapper">
				<image src="../../../static/history/tongji.png" id="smallIcon" style="width:84upx;height: 84upx;"></image>
				<p style="margin-left: 14upx;">统计结论</p>
			</view>
			<!-- 四个分析内容 -->
			<view class="fenxi_wapper">
				<view class="single_fenxi"> 
					<!-- 分析结果 -->
					<view class="fenxi_data">
						<p>0784环</p>
					</view>
					<!-- 分析内容 -->
					<view class="fenxi_title">
						每次平均总环数
					</view>
				</view>
				
				<view class="single_fenxi">
					<!-- 分析结果 -->
					<view class="fenxi_data">
						<p>7环</p>
					</view>
					<!-- 分析内容 -->
					<view class="fenxi_title" style="background-color: #FAC858;">
						上靶环数最多
					</view>
				</view>
				
				<view class="single_fenxi">
					<!-- 分析结果 -->
					<view class="fenxi_data">
						<p>偏右上</p>
					</view>
					<!-- 分析内容 -->
					<view class="fenxi_title" style="background-color: #55aa7f;">
						平均打靶习惯
					</view>
				</view>
				
				<view class="single_fenxi">
					<!-- 分析结果 -->
					<view class="fenxi_data">
						<p>-02.37%</p>
					</view>
					<!-- 分析内容 -->
					<view class="fenxi_title" style="background-color: #00aaff;">
						近5次成绩趋势
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				//uchart表格
				chartData : {
					//横坐标：打靶日期
					categories: ["20212023", "2022024", "20220225", "20220226", "20220227"],
					series: [{
						"name": "第一次",
						"data": [10, 6, 7, 8, 9]
					}, {
						"name": "第二次",
						"data": [9, 10, 7, 6, 8]
					}, {
						"name": "第三次",
						"data": [8, 6, 7, 7, 10]
					}, {
						"name": "第四次",
						"data": [6, 8, 7, 8, 9]
					}, {
						"name": "第五次",
						"data": [7, 6, 7, 8, 9]
					}]
				}
			}
		}
	}
</script>

<style>
	@import url("historyLog");
</style>

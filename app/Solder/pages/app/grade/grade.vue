<template>
	<view class="page" style="background-color: white;display: flex;flex-direction: column;align-items: center;height: 1800upx;">
		<!-- 头部：title + 视频 + 信息按钮 -->
		<view class="top page-block">
			<view class="title">实 时 靶 面</view>
			<view class="video">   <!-- 实时打靶视频 -->
				<image src="../../../static/history/real_Daba.jpg" mode=""></image>
			</view>
			<view class="info">
				<view class="info_single">战士 : 刘雨昕</view>
				<view class="info_single" style="background-color:#ffd426;">靶位 : 一号</view>
			</view>
		</view>
				
		<!-- 底部：成绩分析 -->
		<view class="middle page-block">
			<view class="m_single">
				<p style="font-size: 40upx;color:white; font-weight: bold;">4 次</p>
				<p>本次总计上靶</p>
			</view>
			<view class="m_single"> 
				<p style="font-size: 40upx;color:white; font-weight: bold;">30 环</p>
				<p>本次总计环数</p>
			</view>
			<view class="m_single">
				<p style="font-size: 40upx;color:white; font-weight: bold;">+1 次</p>
				<p>相较上一次</p>
			</view>
			<view class="m_single">
				<p style="font-size: 40upx;color:white; font-weight: bold;">+2 环</p>
				<p>相较上一次</p>
			</view>
		</view>
		
		<!-- 中部：表格 -->
		<view class="grade_wapper page-block">
			<view class="grade_content">
				<view class="charts-box">
				  <qiun-data-charts
				    type="line"
				    :chartData="chartData"
				    background="none"
				  />
				</view>
			</view>
		</view>
		
	</view> 
</template>

<script>
	export default{
		data(){
			return{
				chartData:{
					categories: ["2月21日", "2月22日", "2月23日", "2月24日", "2月25日"],
					series:[{
				    	name:'打靶总计环数',
				    	data:[32, 25, 31, 28, 30]
					},{
						name:'总计上靶次数',
						data:[4, 6, 2, 3, 4]
					}
					]
				}
			}
		},
		methods: {
		        
		}
	}
</script>

<style>
	@import url("grade");
</style>

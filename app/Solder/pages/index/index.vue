<template>
	<view class="content">
		<!-- 头部title -->
		<view class="top">
			<p>智慧靶感知系统</p>
			<view class="title">
				<p>人工智能实时报靶 上靶行为数据分析</p>
			</view>
		</view>
		
		<!-- logo -->
		<view id="logo_wapper">
			<image src="../../static/logo.png" mode="" class="logo"></image>
		</view>
		
		<!-- 中间按钮部分 -->
		<view class="middle">
			<navigator url="../app/login/leader_login" hover-class="navigator-hover">
				<view id="card" style="background-color: #DD524D;">指导员登录</view>
			</navigator>
			<navigator url="../app/login/soldier_login" hover-class="navigator-hover">
				<view id="card" style="background-color: #F0AD4E;">战士登录</view>
			</navigator>
		</view>
		<view class="bottom"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	@import url("index.css");
</style>

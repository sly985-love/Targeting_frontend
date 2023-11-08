<template>
	<view class="page">
		<!-- 头部 start -->
		<view class="page-block header">
			<image src="../../../static/logo.png" class="h_img"></image>
			<view class="h_content">
				<view class="name">
					<view class="name_txt" style="margin-bottom: 10upx;">刘雨昕</view>
				</view>
				<view class="id">
					<view class="id_box">第二部队</view>
					<view class="id_num">战士</view>
				</view>
			</view>
		</view>
		<!-- 头部 end -->
		
		<!-- 下部 start-->
		<view class="line" style="width: 100%;"></view>
		<view class="main_wapper">
			<!-- 单个菜单栏 -->		
			<navigator url="">
				<view class="page-block m_single">
						<image src="../../../static/history/设置.jpg" class="s_img"></image>
						<view class="s_title">个人设置</view>
						<uni-icons type="arrowright" size="25" color="#999999"></uni-icons>
				</view>
			</navigator>
			
			<view class="page-block m_single"  @click="tel">
					<image src="../../../static/history/联系后台.png" class="s_img"></image>
					<view class="s_title">联系后台</view>
					<uni-icons type="arrowright" size="25" color="#999999"></uni-icons>
			</view>
			
			<navigator url="../login/soldier_login">
				<view class="page-block m_single">
						<image src="../../../static/history/我的收藏.png" class="s_img"></image>
						<view class="s_title">退出登录</view>
						<uni-icons type="arrowright" size="25" color="#999999"></uni-icons>
				</view>
			</navigator>
			
		</view>
		<!-- 下部 end-->
	</view>
</template>

<script>
	import uniIcons from "@/components/uni-icons/uni-icons.vue"
	export default {
		components:{
			uniIcons
		},
		data() {
			return {
			}
		},
		onLoad() {
			
		},
		methods: {
			tel(){
				uni.showModal({
				    title: '联系我们',
				    content: 'tel 17323563287',
				    success: function (res) {
				        if (res.confirm) {
				            console.log('点击拨打');
							uni.makePhoneCall({
							    phoneNumber: '17323563287' //仅为示例
							});
				        } else if (res.cancel) {
				            console.log('取消拨打');
				        }
				    }
				});
			}
		},
	}
</script>

<style>
	@import url("me");
</style>

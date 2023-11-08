<template>
	<view class="page">
		<!-- 头部导航栏：吸顶 -->
		<view class="header" id="boxFixed" :class="{'is_fixed' : isFixed}">
			<navigator url="../nowBawei/nowBawei">实时靶位</navigator>
			<navigator url="../BaweiLog/BaweiLog">实时记录</navigator>
			<navigator url="../BaweiTongJi/BaweiTongJi">实时统计</navigator>
			<navigator url="" style="border-bottom: #DD524D 8upx solid;color:#000000;">我的</navigator>
		</view>
		
		<!-- real头部 -->
		<view class="page-block realHeader">
			<image src="../../../static/logo.png" class="h_img"></image>
			<view class="h_content">
				<view class="name">
					<view class="name_txt" style="margin-bottom: 10upx;">刘雨昕</view>
				</view>
				<view class="id">
					<view class="id_box">第二部队</view>
					<view class="id_num">指导员</view>
				</view>
			</view>
		</view>
		
		<!-- 下部 start-->
		<view class="line" style="width: 100%;"></view>
		<view class="main_wapper">
			<!-- 单个菜单栏 -->	
			
			<!-- 只有当身份为超级管理员 才有这一项 -->
			<navigator url="">
				<view class="page-block m_single">
						<image src="../../../static/history/设置.jpg" class="s_img"></image>
						<view class="s_title">指导员管理</view>
						<uni-icons type="arrowright" size="25" color="#999999"></uni-icons>
				</view>
			</navigator>
			
			<navigator url="">
				<view class="page-block m_single">
						<image src="../../../static/history/设置.jpg" class="s_img"></image>
						<view class="s_title">靶位管理</view>
						<uni-icons type="arrowright" size="25" color="#999999"></uni-icons>
				</view>
			</navigator>
			
			<navigator url="">
				<view class="page-block m_single">
						<image src="../../../static/history/设置.jpg" class="s_img"></image>
						<view class="s_title">战士管理</view>
						<uni-icons type="arrowright" size="25" color="#999999"></uni-icons>
				</view>
			</navigator>
			
			<view class="page-block m_single"  @click="tel">
					<image src="../../../static/history/联系后台.png" class="s_img"></image>
					<view class="s_title">联系后台</view>
					<uni-icons type="arrowright" size="25" color="#999999"></uni-icons>
			</view>
			
			<navigator url="../../app/login/leader_login">
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
			return{
				isFixed: false,
				offsetTop: 0
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
		//回调中移除监听
		destroyed() {
			window.removeEventListener('scroll', this.handleScroll)
		}

		
	}
</script>

<style>
	@import url("leaderMe");
</style>

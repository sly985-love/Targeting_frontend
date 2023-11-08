<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	/*每个页面公共css */
		/*每个页面公共css--全局 */
		/*page同y页面的<view class="">映射*/
		.page {
			width:100%;
			height:fit-content;
			/* height:100%; */
			background-color:#F1F1F1; /*背景色*/
			position:absolute; /*绝对定位*/	
		}
		
		.line{
			width:85%;
			height:2upx;
			/* background-color:#C0C0C0; */
			box-shadow: 1upx 2upx #C0C0C0;
			margin: 0 auto;
		}
		
		/*页面白色公共块*/
		.page-block{  
			background-color: #FFFFFF;
		}
		
		/* 小图标 */
		#smallIcon{
			width: 60upx;
			height: 60upx;
		}
</style>

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
	page {
		font-family: PingFangSC, PingFang SC;
		font-weight: bold;
		background-color:  #F5F5F5;
	}
	
	button::after {
	  border: none;
	}
	
	swiper,
	scroll-view {
	  flex: 1;
	  overflow: hidden;
	}
	
	image {
	  width: 100%;
	  height: 100%;
	  vertical-align: middle;
	} 
	
	/* 两行省略 */
	.ellipsis {
	  overflow: hidden;
	  text-overflow: ellipsis;
	  display: -webkit-box;
	  -webkit-line-clamp: 2;
	  -webkit-box-orient: vertical;
	}
	
	::-webkit-scrollbar {
	  display: none;
	  width: 0;
	  height: 0;
	  color: transparent;
	}
</style>

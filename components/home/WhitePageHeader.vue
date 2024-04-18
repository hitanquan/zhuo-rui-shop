<template>
	<view class="navbar" :style="{ paddingTop: navBarHeight + 60 + 'rpx'}">
		<!--门店名称 -->
		<view class="location">
			<image class="location-image" src="@/static/home/location.png"/>
			<text class="location-text">{{locationText}}</text>
			<image class="arrow-image" src="@/static/home/arrow-down.png"/>
		</view>
		<!-- 搜索框 -->
		<view class="search">
			<view class="left">
				<image class="icon-search" src="@/static/home/search.png"/>
				<input class="text-search" type="text" placeholder="输入搜索内容"/>
			</view>
			<view class="right">
				<button class="button-search">搜索</button>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	name: 'WhitePageHeader',
	props: {
		navBarHeight: {
			type: Number,
			default: 0,
		}
	},
	data() {
		return {
			locationText: '酒世家海沧店',
		};
	}
}
</script>

<style scoped lang="scss">
/* 自定义导航条 */
.navbar {
	background-color: #fff;
	height: 166rpx;
  .location {
    display: flex;
    align-items: center;
    height: 64rpx;
    padding-left: 30rpx;
    .location-image {
      width: 32rpx;
      height: 40rpx;
    }
    .location-text {
      line-height: 28rpx;
			color: black;
      margin: 2rpx 5px 0 10rpx;
      font-size: 32rpx;
    }
		.arrow-image {
			width: 16rpx;
			height: 12rpx;
		}
  }
  .search {
    display: flex;
    align-items: center;
  	justify-content: space-between;
  	width: 686rpx;
    height: 60rpx;
    padding-left: 26rpx;
    margin: 16rpx 20rpx;
    font-size: 28rpx;
    border-radius: 38rpx;
    background-color: #FFFFFF;
  	border: 4rpx solid #F2F5FA;
  	.left {
  		display: flex;
  		align-items: center;
  		.icon-search {
  			width: 26rpx;
  			height: 26rpx;
  		}
  		.text-search {
  			color: #999999;
				font-size: 24rpx;
  			margin-left: 10rpx;
  		}
  	}
  	.right {
  			width: 108rpx;
  			height: 60rpx;
  		.button-search {
  			width: 108rpx;
  			height: 60rpx;
  			line-height: 60rpx;
  			background: linear-gradient(90deg, #F48839 0%, #F85B3E 100%);
  			border-radius: 38rpx;
  			font-size: 23rpx;
  			color: #FFFFFF;
  		}
  	}
  }
}
</style>
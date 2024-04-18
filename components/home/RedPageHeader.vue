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
	name: 'RedPageHeader',
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
	background-image: url("data:image/png;base64,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");
	// background: url("../static/home/homeTopBg.png");
	background-size: cover;
	background-repeat: no-repeat;
	display: flex;
	flex-direction: column;
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
			color: #fff;
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

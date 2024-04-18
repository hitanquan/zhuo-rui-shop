<template>
	<view class="good">
		<scroll-view scroll-x scroll-with-animation style="white-space: nowrap;">
			<view class="scroll-certificate-container">
				<navigator
				 class="good-item"
				 v-for="(item,index) in goodList"
				 :key="index"
				 :url="`/pages/goods/goods?id=${index}`"
				>
				 <image class="good-img" mode="aspectFill" :src="item.picture"/>
				 <view class="good-name">
					<text>{{ item.name }} </text>
				 </view>
				 <view class="price-info-container">
					 <view class="price-info">
						<view>
							<text class="small">¥</text>
							<text>{{ item.price }}</text>
						</view>
						 <text class="old-price">¥100.00</text>
					 </view>
					 <view class="tag-view">
						<text class="text">选它</text>
					 </view>
				 </view>
			 </navigator>
		 </view>
	</scroll-view>
 </view>
</template>

<script>
	export default {
		name:"CoustomGoodCard",
		props: {
			goodList: {
				type: Array,
				default: [],
			}
		}
	}
</script>

<style scoped lang="scss">
// 商品样式
.good {
	padding: 0 20rpx;
	.scroll-certificate-container {
		display: flex;
	}
  .good-item {
    width: 176rpx;
		height: 242rpx;
    padding: 24rpx 20rpx 20rpx;
    margin: 5rpx;
    border-radius: 12rpx;
    background-color: #fff;
		.good-img {
			width: 100%;
			height: 142rpx;
		}
		.good-name {
			display: flex;
			height: 50rpx;
			font-size: 20rpx;
			color: #262626;
			overflow: hidden;
			text-overflow: ellipsis;
			display: -webkit-box;
			-webkit-line-clamp: 2;
			-webkit-box-orient: vertical;
		}
		.price-info-container {
			display: flex;
			.price-info {
				line-height: 1;
				margin-right: 15rpx;
				padding-top: 4rpx;
				color: #cf4444;
				font-size: 26rpx;
				.old-price {
					width: 60rpx;
					height: 22rpx;
					font-size: 16rpx;
					color: #999999;
					line-height: 22rpx;
					text-decoration: line-through; 
				}
				.small {
					font-size: 80%;
				}
			}
			.tag-view {
				display: flex;
				width: 60rpx; 
				height: 32rpx;
				line-height: 32rpx;
				text-align: center;
				background: linear-gradient( 90deg, #F48839 0%, #F85B3E 100%);
				border-radius: 4rpx;
				.text {
					width: 60rpx;
					height: 32rpx;
					font-size: 20rpx;
					color: #fff;
				}
			}
		}
	}
}
</style>

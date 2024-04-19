<template>
 <view class="card-container">
	<scroll-view
	 	scroll-x
		scroll-with-animation 
		style="white-space: nowrap; top: 0;"
		class="sticky"
	 >
	 <view class="nav-tab">
		 <view class="nav-tab-item">
		   <text class="nav-name" v-for="(item,index) in firstNavList" :key="index">
				{{ item}}
			 </text>
		 </view>
		 <view class="nav-tab-item">
		   <text class="nav-name bg" 
				 v-for="(item,index) in secondNavList" :key="index">
				{{item}}
			 </text>
		 </view>
	 </view>
	</scroll-view>
	
	<scroll-view
	 	scroll-y
		scroll-with-animation 
		@scroll="rightScroll"
	 >
		<view class="good">
		 <navigator
			 class="good-item"
			 v-for="(item,index) in goodList"
			 :key="index"
			 :url="`/pages/JobConsultation/JobConsultation?id=${index}`"
		 >
			 <image class="image" mode="aspectFill" :src="item.picture"/>
			 <view class="good-name">
					<view class="tag-view">
							<text class="text">推荐</text>
					</view>
					<text class="name">{{ item.name }} </text>
			 </view>
			 
			 <view class="good-price">
				 <view class="price">
					 <view>
						<text class="small">¥</text>
						{{ item.price }}
					 </view>
					 <view class="old-price">¥100.00</view>
				 </view>
				 <view class="tag-view">
				 		<text class="text">选规格</text>
				 </view>
			 </view>
			 
			 <view class="tag-view">
			 		<text class="text">标签名称</text>
			 </view>
		 </navigator>
	 </view>
	</scroll-view>
	 
	<view class="loading-text">
		{{ finish ? '没有更多数据~' : '正在加载...' }}
	</view>
 </view>
</template>

<script>
	export default {
		name:"CoustomCard",
		props: {
			goodList: {
				type: Array,
				default: [],
			},
			isSticky: {
				type: Boolean,
				default: false
			}
		},
		data() {
			return {
				firstNavList: ['店长推荐','啤酒每天','红酒世界','白酒','洋酒'],
				secondNavList: ['为你推荐','冰啤畅饮','醇厚优雅','高贵不贵','畅饮奢华'],
				finish: true,
			}
		}
	}
</script>

<style scoped lang="scss">
.sticky {
	position: sticky;
	z-index: 99;
	background-color: #F2F5FA;
}

.card-container {
	flex: 1;
	//分类导航
	.nav-tab {
		width: 718rpx;
		height: 120rpx;
		padding-top: 20rpx;
		.nav-tab-item {
			line-height: 1;
			padding: 8rpx 0;
			.nav-name {
				width: 100rpx;
				height: 28rpx;
				text-align: center;
				display: inline-block;
				font-size: 32rpx;
				color: #333333;
				margin: 0 30rpx;
			}
			.bg {
				font-size: 18rpx;
				color: #999999;
			}
			.bg:nth-child(1) {
				height: 32rpx;
				line-height: 32rpx;
				background: linear-gradient(90deg, #F48839 0%, #F85B3E 100%);
				border-radius: 14rpx;
				color: #fff;
			}
		}
}

	// 商品卡片
	.good {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		padding: 0 20rpx;
		.good-item {
			width: 304rpx;
			height: 540rpx;
			padding: 24rpx 20rpx 20rpx;
			margin-bottom: 20rpx;
			border-radius: 12rpx;
			overflow: hidden;
			background-color: #fff;
			.tag-view {
				display: flex;
				width: 104rpx;
				height: 36rpx;
				line-height: 36rpx;
				border-radius: 6rpx;
				border: 2rpx solid rgba(153,153,153,0.12);
				.text {
					text-align: center;
					width: 104rpx;
					height: 28px;
					font-size: 20rpx;
					color: #E3202E;
				}
			}
		}
		.image {
			width: 304rpx;
			height: 304rpx;
		}
		.good-name {
			display: inline-block;
			width: 100%;
			height: 75rpx;
			margin: 10rpx 0;
			font-size: 26rpx;
			color: #333333;
			text-overflow: ellipsis;
			.tag-view {
				display: inline-flex;
				text-align: center;
				background: linear-gradient( 90deg, #F48839 0%, #F85B3E 100%);
				width:62rpx;
				height: 32rpx; 
				line-height: 32rpx;
				border-radius: 6rpx;
				.text {
					width: 60rpx;
					height: 20px;
					font-size: 20rpx;
					color: #fff;
				}
			}
			.name {
				padding-left: 10rpx;
			}
		}
		.good-price {
			padding: 20rpx 0;
			display: flex;
			justify-content: space-between;
			line-height: 1;
			.price {
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
			}
			.tag-view {
				display: flex;
				width: 78rpx; 
				height: 42rpx;
				line-height: 42rpx;
				background: linear-gradient( 90deg, #F48839 0%, #F85B3E 100%);
				.text {
					text-align: center;
					border-radius: 4rpx;
					width: 78rpx;
					height: 28px;
					font-size: 20rpx;
					color: #fff;
				}
			}
			.small {
				font-size: 70%;
			}
		}
}

	// 加载提示文字
	.loading-text {
		text-align: center;
		font-size: 20rpx;
		color: #999999;
		padding: 30rpx 0;
	}
}
</style>

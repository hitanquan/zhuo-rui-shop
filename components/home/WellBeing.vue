<!-- 新人专享模块 -->
<template>
	<view class="page-container">
		<view class="page-card">
			<!-- 标题 -->
			<view class="card-title">
				<view class="card-left">
					<image class="logo-image" src="@/static/home/logo.png"/>
					<text class="logo-text">专属折扣任选一件</text>
				</view>
				<view class="card-right">
					<text class="view-more">查看更多</text>
					<image class="arrow-image" src="@/static/home/arrow.png"/>
				</view>
			</view>
			
			<!-- 券 -->
			<view class="card-certificate">
				<view class="sibianxing-certificate">
					<image class="station-image" src="@/static/home/juxing2.png">
						<text class="station-text">当前站点</text>
					</image>
					<view class="new-certificate-text-catainer">
						<text class="new-certificate-text">我的新人券</text>
					</view>
					<button class="more-certificate-button">
						<text class="more-certificate-text">更多福利</text>
					</button>
				</view>
				<view class="scroll-view-x1">
					<scroll-view scroll-x scroll-with-animation style="white-space: nowrap;">
						<view class="scroll-certificate-container">
							<ScrollCertificate class="certificate" v-for="(item, index) in 8" :key="index"/>
						</view>
					</scroll-view>
				</view>
			</view>
			
			<!-- 商品图 -->
			<view class="scroll-view-x2">
				<scroll-view scroll-x scroll-with-animation style="white-space: nowrap;">
					<view class="scroll-certificate-container">
						<CoustomGoodCard :goodList="jiuList"/>
					</view>
				</scroll-view>
			</view>
		</view>
	</view>
</template>
<script>
	import ScrollCertificate from '@/components/home/ScrollCertificate.vue'
	import CoustomGoodCard from '@/components/home/CoustomGoodCard.vue'
	
	export default {
		name:"WellBeing",
		props: {
			jiuList: {
				type: Array,
				default: [],
			}
		},
		components: {
			ScrollCertificate,
			CoustomGoodCard
		}
	}
</script>

<style scoped lang="scss">
.page-container {
	display: flex;
	align-items: center;
	flex-direction: column;
	margin-top: -260rpx;
}
.page-card {
	display: flex;
	align-items: center;
	flex-direction: column;
	background: url("@/static/home/homeBg.png") no-repeat;
	background-size: contain;
	width: 686rpx;
	height: 580rpx;
	.card-title {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		height: 100rpx;
		.card-left {
			display: flex;
			align-items: center;
			width: 100%;
			height: 100rpx;
			padding: 0 20rpx;
			.logo-image {
				width: 184rpx;
				height: 80rpx;
			}
			.logo-text {
				display: inline-block;
				width: 192rpx;
				height: 100rpx;
				line-height: 100rpx;
				margin-left: 20rpx;
				color: #fff;
				font-size: 24rpx;
			}
		}
		.card-right {
			display: flex;
			align-items: center;
			width: 92rpx;
			height: 32rpx;
			background: linear-gradient(180deg, #FEFEF1 0%, #FFF9AF 100%);
			border-radius: 4rpx 0rpx 0rpx 4rpx;
			text-align: center;
			.view-more {
				width: 90rpx;
				height: 20rpx;
				line-height: 20rpx;
				font-size: 16rpx;
				color: #E32219;
			}
			.arrow-image {
				padding: 0 5rpx;
				width: 8rpx;
				height: 8rpx;
			}
		}
	}
	.card-certificate {
		width: 646rpx;
		height: 166rpx;
		display: flex;
		margin-top: 5rpx;
	
		.sibianxing-certificate {
			width: 216rpx;
			height: 166rpx;
			background: url("@/static/home/sibianxing.png") no-repeat;
			background-size: cover;
			position: relative;
			.station-image {
				width: 96rpx;
				height: 32rpx;
				position: absolute;
				left: 0;
				top: 0;
			}
			.station-text {
				width: 80rpx;
				height: 22rpx;
				position: absolute;
				top: 6rpx;
				left: 14rpx;
				font-size: 16rpx;
				color: #E32219;
			}
			.new-certificate-text-catainer {
				width: 130rpx;
				height: 36rpx;
				position: absolute;
				top: 40rpx;
				left: 40rpx;
				.new-certificate-text {
					color: #fff;
					font-size: 26rpx;
				}
			}
			.more-certificate-button {
				width: 120rpx;
				height: 40rpx;
				position: absolute;
				top: 100rpx;
				left: 40rpx;
				border-radius: 20rpx;
				background: linear-gradient(180deg, #FEFEF1 0%, #FFF9AF 100%);
				.more-certificate-text {
					position: absolute;
					left: 20rpx;
					top: 0;
					width: 88rpx;
					height: 32rpx;
					line-height: 40rpx;
					color: #E32219;
					font-size: 18rpx;
				}
			}
		}
		.scroll-view-x1 {
			width: 430rpx;
			height: 158rpx;
			border: 4rpx solid #FFEBD2;
			border-left: none;
			border-radius: 0 12rpx 12rpx 0;
			.scroll-certificate-container {
				display: flex;
				.certificate {
					padding: 20rpx;
				}
			}
		}
	}
	.scroll-view-x2 {
		display: flex;
		width: 700rpx;
	}
}
</style>
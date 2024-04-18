<template>
	<view :class="{'modal-overlay': isShow}">
		<view v-if="isShow" class="ad_dialog">
			<view class="red-packet-card">
				<view class="red-packet-bg"></view>
				<view class="card-up">
					<image class="logo-image" src="@/static/gift/logo.png" />
					<view class="title">
						<text>恭喜获得价值<text class="title-price">xxx元</text>优惠</text>
					</view>
				</view>
				
				<view class="card-down">
					<scroll-view scroll-y scroll-with-animation>
						<view class="scroll-certificate-container">
							<view class="red-packet-certificate" v-for="(item, index) in 10" :key="index">
								<image class="bg-image" src="@/static/gift/certificate-bg.png" />
								<view class="content">
									<view class="left">
										<image class="tip-image" src="@/static/gift/tip.png">
										<text class="tip-text">盒算专项</text>
										<text class="price"><text class="small">¥</text>300</text>	
									</view>
									<view class="right">
										<text class="certificate-title">优惠券名称</text>
										<text class="certificate-price">满1000可用</text>
										<text class="certificate-time">2024-01-28 14:00到期</text>
									</view>
								</view>
							</view>
						</view>
					</scroll-view>
					
					<view class="button-confirm-bg">
						<view class="button-confirm">
							<button class="button">
								立即收下
							</button>
							<text class="text">优惠券详情可在[我的-优惠券]中查看</text>
						</view>
					</view> 
				</view>
				
				<view class="button-close">
					<button class="button" @click="close">关闭</button>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: 'DialogAdPage',
		data() {
			return {
				isShow: true
			};
		},
		methods: {
			close() {
				this.isShow = false;
			}
		}
	}
</script>

<style scoped lang="scss">
	.modal-overlay {
	  background-color: rgba(0, 0, 0, 0.5); /* 设置蒙版背景颜色和透明度 */
	  position: fixed;
	  top: 0;
	  left: 0;
	  width: 100%;
	  height: 100%;
		z-index: 999;
	}

	.ad_dialog {
		position: fixed;
		top: 25%;
		left: 8%;
		  
		.red-packet-card {
			display: flex;
			position: relative;
			align-items: center;
			flex-direction: column;
			width: 620rpx;
			height: 744rpx;
			background: linear-gradient(180deg, #FFF7EA 0%, #FFFFFE 100%);
			border-radius: 36rpx;
			border: 4rpx solid #FFEBD2;
			.red-packet-bg {
				position: absolute;
				bottom: 0;
				z-index: -99;
				width: 640rpx;
				height:360rpx;
				background-image: url("../static/gift/red-packet-bg.png");
				background-repeat: no-repeat;
				background-size: cover;
			}
			
			.card-up {
				display: flex;
				flex-direction: column;
				align-items: center;
				margin-bottom: 20rpx;
				.logo-image {
					width: 402rpx;
					height: 80rpx;
				}
				
				.title {
					width: 280rpx;
					height: 32rpx;
					padding-top: 20rpx;
					font-size: 24rpx;
					color: #E3202E;
					line-height: 32rpx;
					.title-price {
						width: 80rpx;
						height: 32rpx;
						color: #fff;
						border-radius: 4rpx;
						background: linear-gradient(90deg, #F48839 0%, #F74626 100%);
						margin: 0 4rpx;
						padding: 4rpx;
					}
				}
			}
			
			.card-down {
				display: flex;
				flex-direction: column;
				.scroll-certificate-container {
					display: flex;
					align-items: center;
					flex-direction: column;
					height: 450rpx;
					.red-packet-certificate {
						padding-bottom: 16rpx;
						.bg-image {
							position: absolute;
							width: 576rpx;
							height: 150rpx;
						}
						
						.content {
							display: flex;
							position: relative;
							width: 576rpx;
							height: 150rpx;
							.left {
								width: 180rpx;
								.tip-image {
									position: absolute;
									left: 0;
									width: 92rpx;
									height: 32rpx;
								}
								.tip-text {
									align-items: center;
									position: absolute;
									left: 0;
									top: 6rpx;
									width: 90rpx;
									height: 22rpx;
									line-height: 22rpx;
									font-size: 16rpx;
									text-align: center;
									color: #FFFFFF;
								}
								.price {
									position: absolute;
									left: 20rpx;
									top: 40rpx;
									font-size: 52rpx;
									color: #E3202E;
									.small {
										font-size: 60%;
									}
								}
							}
							
							.right {
								display: flex;
								flex-direction: column;
								padding-left: 20rpx;
								width: 396rpx;
								.certificate-title {
									display: inline-block;
									width: 160rpx;
									height: 44rpx;
									padding-top: 16rpx;
									font-size: 32rpx;
									color: #333333;
									line-height: 44rpx;
								}
								.certificate-price {
									width: 130rpx;
									height: 34rpx;
									padding-top: 5rpx;
									font-size: 24rpx;
									color: #666666;
									line-height: 34rpx;
								}
								.certificate-time {
									width: 214rpx;
									height: 28rpx;
									padding-top: 5rpx;
									font-size: 20rpx;
									color: #999999;
									line-height: 28rpx;
								}
							}
						}
					}
				}
			
				.button-confirm-bg {
					background-image: url("../static/gift/red-packet.png");
					background-repeat: no-repeat;
					background-size: contain;
					.button-confirm {
						display: flex;
						flex-direction: column;
						align-items: center;
						width: 640rpx;
						height: 250rpx;
					}
					.button {
						margin-top: 80rpx;
						width: 400rpx;
						height: 80rpx;
						background: linear-gradient(84deg, #FEFEF1 0%, #FFF9AF 100%);
						border-radius: 40rpx;
						font-size: 42rpx;
						color: #E3202E;
						line-height: 80rpx;
					}
					.text {
						width: 400rpx;
						height: 34rpx;
						font-size: 24rpx;
						color: #FFFFFF;
						padding-top: 20rpx;
						text-align: center;
					}
				}
			}
		}
	}
	
	.button-close {
		width: 140rpx;
		height: 80rpx;
		margin-top: 48rpx;
		.button {
			background: rgba(255,255,255,0.1);
			border-radius: 12rpx;
			border: 2rpx solid rgba(255,255,255,0.43);
			font-size: 24rpx;
			color: #fff;
		}
	}
</style>

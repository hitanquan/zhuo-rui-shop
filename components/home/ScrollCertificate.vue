<template>
	<!-- 新人券 -->
	<view class="certificate-container">
		<view class="scroll-certificate">
			<view class="left-certificate">
				<text class="certificate-money">
					<text style="font-size: 70%;">¥</text>
					30
				</text>
				<text class="certificate-location">厦门可用</text>
				<text class="certificate-price">满299元可用</text>
			</view>
			<view class="right-certificate">
				<image class="red-packet-image" src="@/static/home/red-packet.png"/>
				<button class="red-packet-button">
					<text class="button-text">领取</text>
				</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"ScrollCertificate",
		data() {
			return {
			};
		}
	}
</script>

<style scoped lang="scss">
	.certificate-container {
		display: flex;
		align-items: center;
		margin: 0 -10rpx;
		.scroll-certificate {
			display: flex;
			justify-content: space-evenly;
			width: 268rpx;
			height: 126rpx;
			background-image: url("@/static/home/juxing.png");
			background-size: 268rpx 126rpx;
			background-repeat: no-repeat;
			.left-certificate {
				display: flex;
				flex-direction: column;
				padding: 15rpx 10rpx;
				.certificate-money {
					width: 36rpx;
					height: 36rpx;
					color: #E3202E;
					line-height: 36rpx;
					font-size: 34rpx;
				}
				
				.certificate-location {
					width: 48rpx;
					height: 16rpx;
					padding-top: 2rpx;
					font-size: 12rpx;
					background: linear-gradient(90deg, #F2E64F 0%, rgba(254,254,241,0) 100%);
					border-radius: 12rpx;
					color: #E3202E;
					line-height: 16rpx;
					margin: 12rpx 0;
				}
				
				.certificate-price {
					width: 110rpx;
					height: 28rpx;
					font-size: 20rpx;
					color: #E3202E;
					line-height: 28rpx;
				}
			}
			
			.right-certificate {
				display: flex;
				flex-direction: column;
				padding: 15rpx 0;
				.red-packet-image {
					width: 88rpx;
					height: 72rpx;
				}
				
				.red-packet-button {
					width: 72rpx;
					height: 36rpx;
					background: linear-gradient(90deg, #F48839 0%, #F85B3E 100%);
					line-height: 25rpx;
					border-radius: 16rpx;
					.button-text {
						position: absolute;
						top: 6rpx;
						left: 20rpx;
						font-size: 20rpx;
						color: #FFFFFF;
					}
				}
			}
		}
	}
</style>
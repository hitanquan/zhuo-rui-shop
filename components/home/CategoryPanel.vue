<template>
	<view class="category-container">
		<view class="category">
		  <navigator
		    class="category-item"
		    hover-class="none"
		    url="pages/JobConsultation/JobConsultation"
		    v-for="(item, index) in Data"
		    :key="index"
		  >
		    <image class="icon" :src="item.icon"></image>
		    <text class="text">{{ item.name }}</text>
		  </navigator>
			<!-- 指示点 -->
			<view class="indicator">
				<text
					v-for="(item, index) in 3"
					:key="index"
					class="dot"
					:class="{ active: index === activeIndex }"
				></text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: 'CategoryPanel',
		props: {
			Data: {
				type: Array,
				default: [],
			}
		},
		data() {
			return {
				activeIndex: 0
			};
		},
	}
</script>

<style scoped lang="scss">
	.category-container {
		display: flex;
		justify-content: center;
		
		/* 前台类目 */
		.category {
			width: 686rpx;
			height: 374rpx;
		  margin: 20rpx 32rpx;
		  padding: 32rpx 0;
		  display: flex;
			position: relative;
		  flex-wrap: wrap;
			border-radius: 12rpx;
			justify-content: space-around;
			background-color: #fff;
		  .category-item {
		    width: 120rpx;
		    display: flex;
		    flex-direction: column;
		    align-items: center;
		
		    .icon {
		      width: 88rpx;
		      height: 88rpx;
		    }
		    .text {
		      font-size: 26rpx;
		      color: #666;
					padding-top: 8rpx;
		    }
		  }
			
			.indicator {
				position: absolute;
				left: 0;
				right: 0;
				bottom: 16rpx;
				display: flex;
				justify-content: center;
				.dot {
					width: 20rpx;
					height: 6rpx;
					margin: 0 8rpx;
					border-radius: 6rpx;
					background-color: gainsboro;
				}
				.active {
					background-color: red;
				}
			}
		}
	}
</style>

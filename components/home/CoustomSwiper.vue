<template>
	<view class="page-container">
		<!-- 筛选项 -->
		<view class="scroll-view-x">
			<scroll-view
				scroll-x
				scroll-with-animation 
				style="white-space: nowrap;"
			>
				<view class="fliterList" v-for="(item,index) in fliterListData" :key="index"
					@click="onClickFliterListItem(item,index)">
					<view class="fliterListItem">
						{{item.name}}
					</view>
				</view>
			</scroll-view>
		</view>
		
		<!-- 轮播图 -->
		<view class="swiper-box">
			<swiper :autoplay="true" :interval="3000" :duration="1000">
				<swiper-item v-for="(item,index) in Data" :key="index">
					<image :src="item.img" class="swiperItem"></image>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	
	export default {
		name:"CoustomSwiper",
		props: {
			Data: {
				type: Array,
				default: [],
			},
			fliterListData: {
				type: Array,
				default: [],
			}
		},
		data() {
			return {
			};
		},
		methods: {
			onClickFliterListItem(item, index) {
			}
		}
	}
</script>

<style scoped lang="scss">
.page-container {
	background-image: url("../../static/home/swiperBg.png");
	height: 612rpx;
}
.scroll-view-x {
	padding: 4rpx 34rpx;
	.fliterList {
		display: inline-block;
		margin-right: 20rpx;
		background-color: rgba(255, 255, 255, 0.1);
		border-radius: 22rpx;
		padding: 2px 10px;
		.fliterListItem {
			color: rgba(255, 255, 255, 1);
			font-size: 24rpx;
			font-weight: normal;
			text-align: center;
			white-space: nowrap;
		}
	}
}
.swiper-box {
	padding: 24rpx 34rpx;
	.swiperItem {
		width: 100%;
		height: 260rpx;
	}
}
</style>
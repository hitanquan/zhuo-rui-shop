<template>
	<view class="viewport">
		<DialogAdPage v-if="adDialogs"/>
		<RedPageHeader :navBarHeight="navBarHeight" v-if="isDisplayPageHeader"/>
		<WhitePageHeader :navBarHeight="navBarHeight" v-if="!isDisplayPageHeader"/>
		<!-- 滚动容器 -->
		<scroll-view
			class="scroll-view"
			scroll-y
			@scroll="rightScroll"
		>
			<CoustomSwiper :Data="shopBannerList" :fliterListData="shopFliterList"/>
			<WellBeing :jiuList="jiuList"/>
			<CategoryPanel :Data="shopCategoryList"/>
			<CoustomCard :goodList="shopGoodList" />
		</scroll-view>
	</view>
</template>

<script>
	import DialogAdPage from '@/components/DialogAdPage.vue'
	import RedPageHeader from '@/components/home/RedPageHeader.vue'
	import WhitePageHeader from '@/components/home/WhitePageHeader.vue'
	import CategoryPanel from '@/components/home/CategoryPanel.vue'
	import CoustomSwiper from '@/components/home/CoustomSwiper.vue'
	import WellBeing from '@/components/home/WellBeing.vue'
	import CoustomCard from '@/components/home/CoustomCard.vue'
	import Data from '@/util/data.js'

	export default {
		components: {
			DialogAdPage,
			RedPageHeader,
			WhitePageHeader,
			CategoryPanel,
			CoustomSwiper,
			WellBeing,
			CoustomCard
		},
		data() {
			return {
				isDisplayPageHeader: true,  // 是否显示页面头部组件
				adDialogs: false, //是否显示弹窗广告
				navBarHeight: 0, // 状态栏高度
				shopCategoryList: [
					{
						name: '啤酒',
						icon: '../../static/home/pijiu.png'
					},
					{
						name: '白酒',
						icon: '../../static/home/baijiu.png'
					},
					{
						name: '葡萄酒',
						icon: '../../static/home/putaojiu.png'
					},
					{
						name: '洋酒',
						icon: '../../static/home/yangjiu.png'
					},
					{
						name: '鸡尾酒',
						icon: '../../static/home/jiweijiu.png'
					},
					{
						name: '下酒菜',
						icon: '../../static/home/xiajiucai.png'
					},
					{
						name: '名酒',
						icon: '../../static/home/mingjiu.png'
					},
					{
						name: '饮料',
						icon: '../../static/home/yinliao.png'
					},
					{
						name: '邀请有礼',
						icon: '../../static/home/gift.png'
					},
					{
						name: '新人专享',
						icon: '../../static/home/red-packet.png'
					}
				]
				, //酒品分类数据
				shopBannerList: [
					{
						img: '../../static/home/banner.png'
					},
					{
						img: '../../static/home/banner.png'
					}
				], //轮播图数据
				shopFliterList: [
					{
						name: "百威"
					},
					{
						name: "青岛"
					},
					{
						name: "茅台"
					},
					{
						name: "黄盖波分"
					},
					{
						name: "习酒1988"
					},
					{
						name: "麦卡伦"
					}
				], //筛选项数据
				shopGoodList: [], //商品列表数据
				jiuList: [] //酒列表数据
			}
		},
		onLoad() {	
			// this.adDialogs = true
			this.navBarHeight = uni.getSystemInfoSync().statusBarHeight;
			this.shopGoodList = Data.goodList
			this.jiuList = Data.jiuList
		},
		methods: {
			rightScroll(e) {
				const scrollTop = e.detail.scrollTop;
				var opacity = scrollTop / 150;
				if (opacity >= 1) {
					this.isDisplayPageHeader = false;
				} else {
					this.isDisplayPageHeader = true;
				}
			},
		}
	}
</script>

<style lang="scss">
page {
	height: 100%;
	overflow: hidden;
} 

.viewport {
	height: 100%;
	display: flex;
	flex-direction: column;
}
</style>
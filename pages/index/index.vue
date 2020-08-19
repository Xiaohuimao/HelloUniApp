<template>
	<view class="content">
		<!-- 顶部搜索框 -->
		<u-search placeholder="请输入您要搜索的商品、店铺" v-model="keyword" :show-action="action"></u-search>
		<u-tabs name="catName" :list="list" :current="current" @change="change" bar-height="6" bar-width="40"></u-tabs>
		<u-swiper :list="swiperlist"></u-swiper>
		<u-grid :col="3" :border="isBorder">
			<u-grid-item>
				<u-icon name="photo" :size="46"></u-icon>
				<view class="grid-text">图片</view>
			</u-grid-item>
			<u-grid-item>
				<u-icon name="lock" :size="46"></u-icon>
				<view class="grid-text">锁头</view>
			</u-grid-item>
			<u-grid-item>
				<u-icon name="hourglass" :size="46"></u-icon>
				<view class="grid-text">沙漏</view>
			</u-grid-item>
			<u-grid-item>
				<u-icon name="photo" :size="46"></u-icon>
				<view class="grid-text">图片</view>
			</u-grid-item>
			<u-grid-item>
				<u-icon name="lock" :size="46"></u-icon>
				<view class="grid-text">锁头</view>
			</u-grid-item>
			<u-grid-item>
				<u-icon name="hourglass" :size="46"></u-icon>
				<view class="grid-text">沙漏</view>
			</u-grid-item>
			<u-grid-item>
				<u-icon name="photo" :size="46"></u-icon>
				<view class="grid-text">图片</view>
			</u-grid-item>
			<u-grid-item>
				<u-icon name="lock" :size="46"></u-icon>
				<view class="grid-text">锁头</view>
			</u-grid-item>
			<u-grid-item>
				<u-icon name="hourglass" :size="46"></u-icon>
				<view class="grid-text">沙漏</view>
			</u-grid-item>
		</u-grid>
		<u-notice-bar mode="horizontal" :list="noticeList"></u-notice-bar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				keyword: '',
				action: false,
				list: [],
				current: 0,
				isScroll: false,
				swiperlist: [
					{
						image: 'https://cdn.uviewui.com/uview/swiper/1.jpg',
						title: '昨夜星辰昨夜风，画楼西畔桂堂东'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/2.jpg',
						title: '身无彩凤双飞翼，心有灵犀一点通'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/3.jpg',
						title: '谁念西风独自凉，萧萧黄叶闭疏窗，沉思往事立残阳'
					}
				],
				noticeList: [
					'寒雨连江夜入吴',
					'平明送客楚山孤',
					'洛阳亲友如相问',
					'一片冰心在玉壶'
				],
				isBorder: false
			}
		},
		components: {

		},
		onLoad() {
			this.$u.api.getHomeTabList().then(res => {
				// console.log(res.data);
				this.list = res.data;
			})
		},
		methods: {
			change(index) {
				this.current = index;
			},
			// 网络请求相关

		}
	}
</script>

<style lang="scss">
	.content {
		background-color: $uni-page-bg;
		min-height: calc(100vh - 100rpx);

		.u-search {
			background-image: linear-gradient(180deg, #c61b1b, #d32a29);
			height: 120rpx;

			::v-deep .u-content {
				background: transparent !important;

				.u-icon-wrap {
					display: none;
				}

				.u-input {
					color: #333333 !important;
					background: rgba(255, 255, 255, 0.2) !important;
					border-radius: 30rpx;
					width: 614rpx;
					height: 60rpx;
					padding-left: 20rpx;

					.uni-input-placeholder {
						color: #FFFFFF !important;
					}
				}

				.u-close-wrap {
					position: relative;
					left: -70rpx;
				}
			}

		}
	}
</style>

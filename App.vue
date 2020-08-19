<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/* 注意要写在第一行，同时给style标签加入lang="scss"属性 */
		@import "uview-ui/index.scss";
	/*每个页面公共css */
	.uni-app--showtabbar uni-page-wrapper:after {
		height: 80rpx;
		height: calc(80rpx + constant(safe-area-inset-bottom));
		height: calc(80rpx + env(safe-area-inset-bottom));
	}

	uni-tabbar {
		.uni-tabbar {
			// tab 背景
			// background-color: rgba(57, 181, 74, 0.1) !important; // tab 背景色
			// background-image: linear-gradient(to top, #a80077, #66ff00) !important; // tab 背景图片，也可以是渐变色，背景色和背景图片最多选择一个进行设置
			box-shadow:0rpx 0rpx 8rpx 0rpx rgba(32,38,42,0.1);

			.uni-tabbar-border {
				// tabBar 上边框
				// background-color: #e54d42 !important; // tabBar 上边框的颜色
			}

			.uni-tabbar__bd {
				// tabBar 单项
				height: 100rpx !important;

				.uni-tabbar__icon {
					// tabBar 图标
					width: 50rpx !important;
					height: 50rpx !important;
				}

				.uni-tabbar__label {
					// tabBar 文字
					font-size: 20rpx !important;
				}
			}
			.uni-tabbar__bd:first-child {
				
			}
		}

		.uni-tabbar~.uni-placeholder {
			height: 80rpx;
		}
	}
</style>

<template>
	<!-- 左右布局区域 -->
	<view class="home-shop">
		<!-- 左侧分类 -->
		<scroll-view class="category-list" scroll-y>
			<view v-for="(item, index) in categories" :key="index" class="category-item"
				:class="{ active: activeIndex === index }" @click="activeIndex = index">
				{{ item }}
			</view>
		</scroll-view>

		<!-- 右侧商品列表 -->
		<scroll-view class="goods-list" scroll-y>
			<view class="goods-item" v-for="(item, index) in goodsList" :key="index">
				<image class="goods-image" :src="item.image" mode="aspectFill"></image>
				<view class="goods-info">
					<text class="goods-name">{{ item.name }}</text>
					<text class="goods-category">{{ item.category }}</text>
					<view class="goods-tags">
						<text class="tag">特价</text>
						<text class="tag">24H发货</text>
					</view>
					<view class="goods-price">
						<text class="price-now">¥{{ item.price }}/份</text>
						<text class="price-old">¥{{ item.oldPrice }}/份</text>
						<view class="cart-btn">
							<uni-icons type="cart" size="18" color="#fff"></uni-icons>
						</view>
					</view>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script setup>
	import {
		ref
	} from 'vue'

	const activeIndex = ref(0)

	const categories = ref([
		'热带水果', '樱桃莓类', '柑橘橙柚', '苹果梨蕉', '奇异果', '瓜类葡萄', '茄果', '菌菇', '葱姜蒜'
	])

	const goodsList = ref([{
			name: '四川爱媛38号可吸果冻橙',
			category: '有机食品 | 水果',
			price: '39.9',
			oldPrice: '45.8',
			image: '/static/images/goods1.jpg'
		},
		{
			name: '四川眉山 爱媛38号可吸果冻橙礼盒装12粒',
			category: '有机食品 | 水果',
			price: '12.8',
			oldPrice: '15.8',
			image: '/static/images/goods2.jpg'
		},
		{
			name: '四川眉山爱媛38号果冻橙',
			category: '有机食品 | 水果',
			price: '12.8',
			oldPrice: '15.8',
			image: '/static/images/goods3.jpg'
		},
		{
			name: '江苏无锡 爱媛38号果冻橙',
			category: '有机食品 | 水果',
			price: '12.8',
			oldPrice: '15.8',
			image: '/static/images/goods4.jpg'
		},
	])
</script>

<style lang="scss" scoped>
	.home-search {
		width: 100%;
		padding: 16rpx 24rpx;
		box-sizing: border-box;
		background: linear-gradient(135deg, #d8237d, #ea2588);

		.search-form {
			display: flex;
			align-items: center;
			background: #ffffff;
			border-radius: 50rpx;
			padding: 14rpx 30rpx;
			height: 50rpx;

			.search-input {
				flex: 1;
				font-size: 28rpx;
				border: none;
				color: #333;
				height: 100%;
			}

			uni-icons {
				margin-left: 10rpx;
				flex-shrink: 0;
			}
		}
	}

	.home-swiper {
		width: 100%;
		padding: 0 24rpx 24rpx;
		box-sizing: border-box;
		background: linear-gradient(180deg, #d8237d, #f2f3f2);

		.swiper-items {
			width: 100%;
			height: 340rpx;
			border-radius: 16rpx;
			overflow: hidden;
		}

		.swiper-image {
			width: 100%;
			height: 100%;
		}
	}

	/* 左右布局 */
	.home-shop {
		display: flex;
		height: calc(100vh - 560rpx); // 减去搜索框+轮播图高度
		background: #f2f3f2;

		// 左侧分类
		.category-list {
			width: 160rpx;
			height: 100%;
			background: #f2f3f2;

			.category-item {
				display: flex;
				align-items: center;
				justify-content: center;
				height: 90rpx;
				font-size: 26rpx;
				color: #666;
				text-align: center;

				&.active {
					background: #ffffff;
					color: #d8237d;
					font-weight: bold;
					border-left: 4rpx solid #d8237d;
				}
			}
		}

		// 右侧商品列表
		.goods-list {
			flex: 1;
			height: 100%;
			background: #ffffff;
			padding: 0 20rpx;
			box-sizing: border-box;

			.goods-item {
				display: flex;
				padding: 20rpx 0;
				border-bottom: 1rpx solid #f5f5f5;

				.goods-image {
					width: 160rpx;
					height: 160rpx;
					border-radius: 8rpx;
					flex-shrink: 0;
				}

				.goods-info {
					flex: 1;
					margin-left: 20rpx;
					display: flex;
					flex-direction: column;
					justify-content: space-between;

					.goods-name {
						font-size: 26rpx;
						color: #333;
						line-height: 1.4;
					}

					.goods-category {
						font-size: 22rpx;
						color: #999;
						margin-top: 6rpx;
					}

					.goods-tags {
						display: flex;
						gap: 10rpx;
						margin-top: 8rpx;

						.tag {
							font-size: 20rpx;
							color: #d8237d;
							border: 1rpx solid #d8237d;
							padding: 2rpx 10rpx;
							border-radius: 4rpx;
						}
					}

					.goods-price {
						display: flex;
						align-items: center;
						margin-top: 10rpx;

						.price-now {
							font-size: 28rpx;
							color: #d8237d;
							font-weight: bold;
						}

						.price-old {
							font-size: 22rpx;
							color: #999;
							text-decoration: line-through;
							margin-left: 10rpx;
						}

						.cart-btn {
							margin-left: auto;
							width: 56rpx;
							height: 56rpx;
							background: #d8237d;
							border-radius: 50%;
							display: flex;
							align-items: center;
							justify-content: center;
						}
					}
				}
			}
		}
	}
</style>
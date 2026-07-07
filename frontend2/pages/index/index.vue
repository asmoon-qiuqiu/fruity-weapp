<template>
	<view class="home-search">
		<view class="search-form">
			<input class="search-input" type="text" name="search" placeholder="搜索内容" placeholder-style="color: #999;" />
			<uni-icons class="search-icon" type="search" size="18" color="#999"></uni-icons>
		</view>

	</view>

	<view class="home-swiper">
		<swiper class="swiper-items" :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item>
				<image class="swiper-image" src="/static/images/banner.jpg" mode=""></image>
			</swiper-item>
			<swiper-item>
				<image class="swiper-image" src="/static/images/banner2.jpg" mode=""></image>
			</swiper-item>
			<swiper-item>
				<image class="swiper-image" src="/static/images/banner3.jpg" mode=""></image>
			</swiper-item>
		</swiper>
	</view>

	<!-- 左右布局区域 -->
	<view class="home-shop">
		<!-- 左侧分类 -->
		
	</view>


</template>
<script setup>
	import {
		ref
	} from 'vue'
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
</style>
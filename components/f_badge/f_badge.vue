<template>
		<text class="badge_wrapper" :style="wraStyle" :class="{'default_size': size === 'default', 'mini_size': size === 'mini'}" v-if="count">{{count}}</text>
</template>

<script>
	export default {
		props: {
			bgColor: {
				type: String,
				default: '#f43'
			},
			count: {
				type: [String, Number]
			},
			offset: {
				type: Number,
				default: 170
			},
			size: {
				type: String,
				default: 'default'
			}
		},
		computed: {
			wraStyle() {
				let offset = this.offset
				console.log(offset)
				return `left: ${this.offset}rpx; background-color: ${this.bgColor}`
			}
		}
	}
</script>

<style scoped>
	.badge_wrapper {
		position: absolute;
		top: 0rpx;
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		border-radius: 40rpx;
		padding: 10rpx;
	}
	.default_size  {
		width: 60rpx;
		font-size: 30rpx;
		line-height: 24rpx;
		text-align: center;
		justify-content: center;
		align-items: center;
		font-weight: bold;
		color: #fff;
	}
	.mini_size {
		/* height: 40rpx; */
		width: 50rpx;
		font-size: 24rpx;
		line-height: 14rpx;
		text-align: center;
		justify-content: center;
		align-items: center;
		font-weight: bold;
		color: #fff;
	}
</style>

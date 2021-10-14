<template>
		<view class="wrapper">
			<view class="header">
				<image src="../../static/logo.png"></image>
			</view>
			<view class="center">
				<u-form v-model="form" ref="uForm">
					<u-form-item prop="readerNumber">
						<span>读者证号</span>
						<u-input :disabled="true"  v-model="form.readerNumber" />
					</u-form-item>
				</u-form>
			</view>
			<view class="bottom">
				<u-button type="primary" shape="circle" @click="submit">解除绑定</u-button>
			</view>
		</view>
</template>

<script>
	export default {
		data () {
			return {
				form: {
					readerNumber: 'TJLD00000547380'
				}
			}
		},
		methods: {
			submit() {
				console.log('解除成功！')
			}
		}
	}
</script>

<style lang="scss" scoped>
	uni-page-body{
		width: 100%;
		height: 100%;
		display:flex;
		flex-direction: column;
		background-color: #f2f2f2;
	}
	.wrapper{
		width: 100%;
		height: 1000rpx;
		display:flex;
		flex-direction: column;
		justify-content:space-around;
		align-items:center; // 子元素垂直居中
		.header{
			width: 100%;
			display:flex;
			justify-content:center;  //子元素水平居中
			align-items:center; // 子元素垂直居中
			image{
				height: 160rpx;
				width: 160rpx;				
			}
		}
		.center{
			width: 100%;
			span{
				color: #909399;
			}
			/deep/.u-form{
				width: 100%;
				display: flex;
				flex-direction: column;
				justify-content:center;  //子元素水平居中
				align-items:center; // 子元素垂直居中	
			}
			/deep/.u-form-item{
				width: 600rpx;
				background-color: #fff;
				box-shadow: #b0b0b0 0rpx 0rpx 12rpx;
			}
			/deep/.u-input{
				flex: initial;
			}
			/deep/.u-form-item--right__content__slot{
				display: flex;
				flex-direction: row;
				justify-content: space-around;
			}
		}
		.bottom{
			width: 450rpx;
		}
	}
</style>

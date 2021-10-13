<template>
		<view class="wrapper">
			<view class="header">
				<image src="../../static/logo.png"></image>
			</view>
			<view class="center">
				<view class="item">
					<uni-easyinput prefixIcon="contact" v-model="value" placeholder="请输入读者证号码"></uni-easyinput>
				</view>
				<view class="item">
					<uni-easyinput prefixIcon="locked" type="password" v-model="value" placeholder="请输入读者证密码"></uni-easyinput>
				</view>
			</view>
			<view class="bottom">
				<u-button type="primary" shape="circle">绑定</u-button>
			</view>
		</view>
</template>

<script>
	export default {
		components: {
		},
		data () {
			return {
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
		height: 80%;
		display:flex;
		flex-direction: column;
		justify-content:space-around;  //子元素水平居中
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
			display:flex;
			flex-direction: column;
			justify-content:center;  //子元素水平居中
			align-items:center; // 子元素垂直居中
			.item{
				width: 80%;
				padding-top: 40rpx;
				/deep/.custom-icon{
					margin-right: 9rpx;
				}
				/deep/.u-content{
					border-radius: 4rpx;
					border: 1px solid #c0c4cc;
					box-shadow: #b0b0b0 0rpx 0rpx 12rpx;
				}
			}			
		}
		.bottom{
			width: 60%;
		}
	}
</style>

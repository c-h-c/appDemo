<template>
		<view class="wrapper">
			<view class="header">
				<image src="../../static/logo.png"></image>
			</view>
			<view class="center">
				<view class="item">
					<xfl-select 
							:list="list"
							:showItemNum="5" 
							:placeholder = "'请选择题名'"
							:selectHideType="'hideAll'"
							focusShowList="true"
							:clearable="false"
					>
					<u-icon name="tushumulu" color="#606266" size="35" custom-prefix="custom-icon" slot="pre-icon"></u-icon>
					</xfl-select>
				</view>
				<view class="item">
					<xfl-select 
							:list="list"
							:showItemNum="5" 
							:placeholder = "'请选择文献类型'"
							:selectHideType="'hideAll'"
							focusShowList="true"
							:clearable="false"
					>
					<u-icon name="wenxianziliao" color="#606266" size="35" custom-prefix="custom-icon" slot="pre-icon"></u-icon>
					</xfl-select>
				</view>
				<view class="item">
					<u-search height="100" placeholder="请输入关键词" v-model="keyword" :show-action="false" shape="square" bg-color="#FFF"></u-search>
				</view>
			</view>
			<view class="bottom">
				<u-button type="primary" shape="circle">搜索</u-button>
			</view>
		</view>
</template>

<script>
	import xflSelect from '../../components/xfl-select/xfl-select.vue';
	export default {
		components: {
			xflSelect
		},
		data () {
			return {
				keyword: '',
				list: [       //要展示的数据
						'苹果',
						'葡萄',
						'芒果',
						'大白菜',
				]
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
				/deep/.show-box{
					height: 3.5em;
					padding: 0 12% 0 3%;
					border-radius: 4rpx;
					box-shadow: #b0b0b0 0rpx 0rpx 12rpx;
				}
				/deep/.placeholder{
					color: #909399;
				}
				/deep/.custom-icon{
					margin-right: 9rpx;
				}
				/deep/.u-content{
					border-radius: 4rpx !important;
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

<template>
		<view class="wrapper">
			<view class="item">
        <xfl-select 
            :list="list"
            :clearable="false"
            :showItemNum="5" 
            :isCanInput="true"  
            :placeholder = "'请选择'"
            :selectHideType="'hideAll'"
						focusShowList="true"
        >
        </xfl-select>
			</view>
			<view class="item">
        <xfl-select 
            :list="list"
            :clearable="false"
            :showItemNum="5" 
            :isCanInput="true"  
            :placeholder = "'请选择'"
            :selectHideType="'hideAll'"
						focusShowList="true"
        >
        </xfl-select>
			</view>
			<view class="item">
				<u-search height="100" placeholder="请输入关键词" v-model="keyword" :show-action="false" shape="square" bg-color="#FFF"></u-search>
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
						{value: '香蕉', disabled: true},
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
		display:flex;
		flex-direction: column;
		justify-content:center;  //子元素水平居中
		align-items:center; // 子元素垂直居中
		background-color: #f2f2f2;
	}
	.wrapper{
		width: 100%;
		display:flex;
		flex-direction: column;
		justify-content:center;  //子元素水平居中
		align-items:center; // 子元素垂直居中
		.item{
			width: 80%;
			padding-top: 20px;
			/deep/.show-box{
				height: 3.5em;
				border-radius: 2px;
				box-shadow: #b0b0b0 0px 0px 6px;
			}
			/deep/uni-input:not(:last-child):before{
				content: "\e61b";
			}
			/deep/.u-content{
				border-radius: 2px;
				border: 1px solid #c0c4cc;
				box-shadow: #b0b0b0 0px 0px 6px;
			}
		}
	}
</style>

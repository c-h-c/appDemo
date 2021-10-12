<template>
	<view class="wrapper">
		<view class="top">
			<u-swiper :list="list"></u-swiper>
		</view>
		<view class="center" @click="goSearch">
			<u-search :disabled="true" height="70" bg-color="#FFF" :show-action="false" placeholder="请输入检索关键字" v-model="keyword"></u-search>
		</view>
		<view class="content">
			<uni-grid :column="3" @change="gridIndex">
				<uni-grid-item v-for="val in gridList" :key="val.id" :index="val.id">
					<view class="gridItem">
						<u-icon :name="val.class" :size="60" :color="val.color"></u-icon>
						<text class="text">{{val.text}}</text>
					</view>
				</uni-grid-item>
			</uni-grid>
		</view>
		<view class="footer">
			<span>技术支持：天津读者之星有限公司</span>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
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
				keyword: '',
				gridList: [
					{
						id: 1,
						class: 'photo',
						color: 'red',
						text:'读者证绑定'
					},
					{
						id: 2,
						class: 'photo',
						color: 'blue',
						text:'个人资料'
					},
					{
						id: 3,
						class: 'photo',
						color: 'pink',
						text:'书目检索'
					},
					{
						id: 4,
						class: 'photo',
						color: 'black',
						text:'借阅记录'
					},
					{
						id: 5,
						class: 'photo',
						color: 'grey',
						text:'图书续借'
					},
					{
						id: 6,
						class: 'photo',
						color: 'red',
						text:'电子书'
					},
					{
						id: 7,
						class: 'photo',
						color: 'blue',
						text:'读者活动'
					},
					{
						id: 8,
						class: 'photo',
						color: 'blue',
						text:'国图移动阅读'
					}
					]
			}
		},
		onLoad() {
		},
		methods: {
			goSearch () {
				// 使用router
				this.$router.push({name: 'books/search'})
			},
			gridIndex (val) {
				console.log(val.detail.index)
				// 使用uni.navigateTo
				uni.navigateTo({
					url: `pages/index/search`
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	uni-page-body,#app{
		height: 100%;
	}
	.wrapper{
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		background-color: #F0F0F0;
		.center{
			padding: 25px;
			/deep/.u-content{
				box-shadow: #888888 0px 0px 6px;
			}
			/deep/.u-content:hover{
				box-shadow: #888888 0px 0px 6px;
				border: 1px solid blue;
				cursor: auto;
			}
		}
		.content{
			padding-bottom: 4rpx;
			.gridItem{
				display: flex;
				flex-direction: column;
				justify-content: center;
				align-items: center;
			}
		}
		/deep/.uni-grid-item__box{
			justify-content: center;
		}
		.footer{
			text-align: center;
			font-size: 12px;
			color: #C9C6C4;
		}
	}
</style>

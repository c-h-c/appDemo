<template>
	<view class="wrapper">
		<view class="top">
			<u-swiper :list="list"></u-swiper>
		</view>
		<view class="center" @click="goSearch">
			<u-search :disabled="true" height="90" bg-color="#FFF" :show-action="false" placeholder="请输入检索关键字" v-model="keyword"></u-search>
		</view>
		<view class="content">
			<u-grid :col="3">
				<u-grid-item bg-color="#F2F2F2" v-for="val in gridList" class="gridItem">
					<u-icon :name="val.class" :size="60" :color="val.color"></u-icon>
					<view class="grid-text">{{val.text}}</view>
				</u-grid-item>
			</u-grid>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
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
						class: 'photo',
						color: 'red',
						text:'图片'
					},
					{
						class: 'photo',
						color: 'blue',
						text:'图片'
					},
					{
						class: 'photo',
						color: 'pink',
						text:'图片'
					},
					{
						class: 'photo',
						color: 'black',
						text:'图片'
					},
					{
						class: 'photo',
						color: 'grey',
						text:'图片'
					},
					{
						class: 'photo',
						color: 'red',
						text:'图片'
					},
					{
						class: 'photo',
						color: 'blue',
						text:'图片'
					}]
			}
		},
		onLoad() {
		},
		methods: {
			goSearch () {
				this.$router.push({name: 'books/search'})
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
		.top{
		}
		.center{
			padding: 30px;
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
		}
	}
</style>

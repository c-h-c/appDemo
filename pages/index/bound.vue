<template>
		<view class="wrapper">
			<view class="header">
				<image src="../../static/logo.png"></image>
			</view>
			<view class="center">
				<u-form v-model="form" ref="uForm">
					<u-form-item prop="readerNumber">
						<u-icon name="shu" size="50" custom-prefix="custom-icon"></u-icon>
						<u-input placeholder="请输入读者证号码" v-model="form.readerNumber" />
					</u-form-item>
					<u-form-item prop="password">
						<u-icon name="mima" size="50" custom-prefix="custom-icon"></u-icon>
						<u-input type="password" placeholder="请输入读者证密码" v-model="form.password" />
					</u-form-item>
				</u-form>
			</view>
			<view class="bottom">
				<u-button type="primary" shape="circle" @click="submit">绑定</u-button>
			</view>
		</view>
</template>

<script>
	const valiMessage = (field) => `请填写正确的${field}`
	const license = /^[0-9A-Za-z,]+$/
	export default {
		components: {
		},
		data () {
			return {
				form: {
					readerNumber: '',
					password: '',
				},
				rules: {
					readerNumber: [{
						required: true,
						message: valiMessage('读者证号码'),
						trigger: ['blur', 'change']
					},
					// 正则判断为字母或数字
					{
						pattern: /^[0-9a-zA-Z]*$/g,
						// 正则检验前先将值转为字符串
						// 使用transform把内容转为string，解决输入值仍然验证不通过的问题
						transform(value) {
							return String(value);
						},
						message: '只能包含字母或数字'
					},
					// 6-8个字符之间的判断
					{
						min: 6,
						max: 20,
						message: '长度在6-8个字符之间'
					}],
					password: {
						required: true,
						transform(value) {
							return String(value);
						},
						message: valiMessage('读者证密码'),
						min: 6,
						max: 16,
						pattern: license,
						trigger: ['change','blur']
					}
				}
			}
		},
		methods: {
			submit() {
				console.log(this.form)
				this.$refs.uForm.validate(valid => {
					console.log(valid)
					if (valid) {
						console.log('验证通过');
					} else {
						console.log('验证失败');
					}
				});
			}
		},
		// 必须要在onReady生命周期，因为onLoad生命周期组件可能尚未创建完毕
		onReady() {
			this.$refs.uForm.setRules(this.rules);
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
			/deep/.u-form{
				width: 100%;
				display: flex;
				flex-direction: column;
				justify-content:center;  //子元素水平居中
				align-items:center; // 子元素垂直居中	
			}
			/deep/.u-form-item{
				width: 600rpx;
				margin-top: 30rpx;
				background-color: #fff;
				box-shadow: #b0b0b0 0rpx 0rpx 12rpx;
			}
			/deep/.custom-icon{
				margin: 0 20rpx;
			}
			/deep/.u-form-item--right__content__slot{
				display: flex;
				flex-direction: row;
			}
			/* #ifdef MP-WEIXIN */
			/deep/.u-input__input{
				width: 450rpx;
			}
			/* #endif */
			/deep/.u-input__right-icon__item{
				margin: 0 20rpx;
			}
		}
		.bottom{
			width: 450rpx;
		}
	}
</style>

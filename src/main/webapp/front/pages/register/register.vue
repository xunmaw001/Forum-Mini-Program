<template>
<view class="content">
	<view class="box" :style='{"padding":"48rpx 0","boxShadow":"24rpx 24rpx 0px rgba(255,255,255,.39)","margin":"0 auto","borderColor":"#ccc","backgroundColor":"#fff","borderRadius":"20rpx","borderWidth":"0","width":"80%","borderStyle":"solid","height":"auto"}'>
		<view class="logo" :style='{"padding":"0 48rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0 auto 24rpx","borderColor":"#ccc","backgroundColor":"#fff","borderRadius":"0","borderWidth":"0","width":"100%","borderStyle":"solid","height":"auto"}' v-if="true">
			<image :style='{"padding":"0","boxShadow":"0 0 0px #59f43e","margin":"0 auto","borderColor":"rgba(128, 89, 73, 1)","borderRadius":"50%","borderWidth":"2rpx","width":"120rpx","borderStyle":"solid","url":"http://codegen.caihongy.cn/20220217/668aa39543bc4153a2182ddd922ec16b.jpg","isShow":true,"height":"120rpx"}' src='http://codegen.caihongy.cn/20220217/668aa39543bc4153a2182ddd922ec16b.jpg' mode="aspectFill"></image>
		</view>
		<view :style='{"padding":"0 48rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0 auto 24rpx","borderColor":"#ccc","backgroundColor":"#fff","borderRadius":"0","borderWidth":"0","width":"100%","borderStyle":"solid","height":"auto"}' v-if="tableName=='yonghu'" class="uni-form-item uni-column">
			<input :style='{"padding":"0 24rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0","borderColor":"rgba(201, 201, 201, 1)","backgroundColor":"#fff","color":"rgba(0, 0, 0, 1)","textAlign":"left","borderRadius":"0","borderWidth":"0 0 2rpx","width":"100%","fontSize":"28rpx","borderStyle":"solid","height":"88rpx"}'  v-model="ruleForm.yonghuming"  type="text"  class="uni-input" name="" placeholder="用户名" />
		</view>
		<view :style='{"padding":"0 48rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0 auto 24rpx","borderColor":"#ccc","backgroundColor":"#fff","borderRadius":"0","borderWidth":"0","width":"100%","borderStyle":"solid","height":"auto"}' v-if="tableName=='yonghu'" class="uni-form-item uni-column">
			<input :style='{"padding":"0 24rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0","borderColor":"rgba(201, 201, 201, 1)","backgroundColor":"#fff","color":"rgba(0, 0, 0, 1)","textAlign":"left","borderRadius":"0","borderWidth":"0 0 2rpx","width":"100%","fontSize":"28rpx","borderStyle":"solid","height":"88rpx"}'  v-model="ruleForm.mima" type="password"  class="uni-input" name="" placeholder="密码" />
		</view>
        <view v-if="tableName=='yonghu'" class="uni-form-item uni-column">
            <input :style='{"padding":"0 24rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0","borderColor":"rgba(201, 201, 201, 1)","backgroundColor":"#fff","color":"rgba(0, 0, 0, 1)","textAlign":"left","borderRadius":"0","borderWidth":"0 0 2rpx","width":"100%","fontSize":"28rpx","borderStyle":"solid","height":"88rpx"}' v-model="ruleForm.mima2" type="password" class="uni-input" name="" placeholder="确认密码" />
        </view>
		<view :style='{"padding":"0 48rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0 auto 24rpx","borderColor":"#ccc","backgroundColor":"#fff","borderRadius":"0","borderWidth":"0","width":"100%","borderStyle":"solid","height":"auto"}' v-if="tableName=='yonghu'" class="uni-form-item uni-column">
			<input :style='{"padding":"0 24rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0","borderColor":"rgba(201, 201, 201, 1)","backgroundColor":"#fff","color":"rgba(0, 0, 0, 1)","textAlign":"left","borderRadius":"0","borderWidth":"0 0 2rpx","width":"100%","fontSize":"28rpx","borderStyle":"solid","height":"88rpx"}'  v-model="ruleForm.xingming"  type="text"  class="uni-input" name="" placeholder="姓名" />
		</view>
		<view :style='{"padding":"0 48rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0 auto 24rpx","borderColor":"#ccc","backgroundColor":"#fff","borderRadius":"0","borderWidth":"0","width":"100%","borderStyle":"solid","height":"auto"}' v-if="tableName=='yonghu'" class="uni-form-item uni-column">
			<picker  @change="yonghuxingbieChange" :value="yonghuxingbieIndex" :range="yonghuxingbieOptions">
				<view :style='{"padding":"0 24rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0","borderColor":"#ccc","backgroundColor":"rgba(128, 89, 73, 1)","color":"rgba(255, 255, 255, 1)","textAlign":"left","borderRadius":"10rpx","borderWidth":"0","width":"100%","lineHeight":"80rpx","fontSize":"28rpx","borderStyle":"solid"}'  class="uni-input">{{ruleForm.xingbie?ruleForm.xingbie:"请选择性别"}}</view>
			</picker>
		</view>
		<view :style='{"padding":"0 48rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0 auto 24rpx","borderColor":"#ccc","backgroundColor":"#fff","borderRadius":"0","borderWidth":"0","width":"100%","borderStyle":"solid","height":"auto"}' v-if="tableName=='yonghu'" class="uni-form-item uni-column">
			<input :style='{"padding":"0 24rpx","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0","borderColor":"rgba(201, 201, 201, 1)","backgroundColor":"#fff","color":"rgba(0, 0, 0, 1)","textAlign":"left","borderRadius":"0","borderWidth":"0 0 2rpx","width":"100%","fontSize":"28rpx","borderStyle":"solid","height":"88rpx"}'  v-model="ruleForm.shoujihaoma"  type="text"  class="uni-input" name="" placeholder="手机号码" />
		</view>
		<button class="btn-submit" @tap="register" type="primary" :style='{"padding":"0","boxShadow":"0 2rpx 12rpx rgba(0,0,0,0)","margin":"0","borderColor":"#ccc","backgroundColor":"rgba(128, 89, 73, 1)","borderRadius":"0 0 120rpx 120rpx","color":"rgba(255, 255, 255, 1)","borderWidth":"2rpx","width":"100%","fontSize":"32rpx","borderStyle":"solid","height":"160rpx"}'>注册</button>
	</view>
</view>
</template>

<style>
	.btn-submit {
		height: auto !important;
		line-height: 160rpx;
	}
</style>
<script>
	export default {
		data() {
			return {
                                yonghuxingbieOptions: [],
                                yonghuxingbieIndex: 0,
				ruleForm: {
				},
				emailcode: "",
				tableName:""
			}
		},
		async onLoad() {
			let res = [];
			let table = uni.getStorageSync("loginTable");
	    		this.tableName = table;

                        // 自定义下拉框值
			if(this.tableName=='yonghu'){
                this.yonghuxingbieOptions = "男,女".split(',');
				this.ruleForm.xingbie=this.yonghuxingbieOptions[0]
			}
			
			this.styleChange()
		},
		methods: {

                        // 下拉变化
                        yonghuxingbieChange(e) {
                                this.yonghuxingbieIndex = e.target.value
                                this.ruleForm.xingbie = this.yonghuxingbieOptions[this.yonghuxingbieIndex]
                        },

			styleChange() {
				this.$nextTick(()=>{
					// document.querySelectorAll('.uni-input .uni-input-input').forEach(el=>{
					//   el.style.backgroundColor = this.registerFrom.content.input.backgroundColor
					// })
				})
			},
			// 获取uuid
			getUUID () {
				return new Date().getTime();
			},
			// 注册
			async register() {
				if((!this.ruleForm.yonghuming) && `yonghu` == this.tableName){
					this.$utils.msg(`用户名不能为空`);
					return
				}
				if((!this.ruleForm.mima) && `yonghu` == this.tableName){
					this.$utils.msg(`密码不能为空`);
					return
				}
                if(`yonghu` == this.tableName && (this.ruleForm.mima!=this.ruleForm.mima2)){
                    this.$utils.msg(`两次密码输入不一致`);
                    return
                }
				if((!this.ruleForm.xingming) && `yonghu` == this.tableName){
					this.$utils.msg(`姓名不能为空`);
					return
				}
				if(`yonghu` == this.tableName && this.ruleForm.shoujihaoma&&(!this.$validate.isMobile(this.ruleForm.shoujihaoma))){
					this.$utils.msg(`手机号码应输入手机格式`);
					return
				}
				await this.$api.register(`${this.tableName}`, this.ruleForm, this.emailcode);
				this.$utils.msgBack('注册成功');;
			}
		}
	}
</script>

<style lang="scss" scoped>
	$color-primary: #b49950;
	.content {
		height: calc(100vh - 44px);
		overflow: auto;
	}
	
	.content:after {
		position: fixed;
		top: 0;
		right: 0;
		left: 0;
		bottom: 0;
		content: '';
				background-image: url(http://codegen.caihongy.cn/20220217/04314405e2aa4c0e81f77b1dd5ca0362.png);
				background-attachment: fixed;
		background-size: cover;
		background-position: center;
	}

	.logo {
		text-align: center;

		image {
			height: 200upx;
			width: 200upx;
			margin: 0 0 60upx;
		}
	}

	.uni-form-item {
		margin-bottom: 40upx;
		padding: 0;

		.uni-input {
			font-size: 30upx;
			padding: 7px 0;
		}
	}

	button[type="primary"] {
		background-color: $color-primary;
		border-radius: 0;
		font-size: 34upx;
		margin-top: 60upx;
	}

	.links {
		text-align: center;
		margin-top: 40upx;
		font-size: 26upx;
		color: #999;

		view {
			display: inline-block;
			vertical-align: top;
			margin: 0 10upx;
		}

		.link-highlight {
			color: $color-primary
		}
	}
.picker-select-input {
	line-height: 88rpx;
}

</style>

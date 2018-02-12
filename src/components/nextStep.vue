<template>
		<div>
			<form>
				<div id='step1' class=''>
					this is step 1
					<input v-model:value = 'num' type='text' />
				</div>
				<div id='step2' class='dialog-tabHide'>
					this is step 2
				</div>
				<div id='step3' class='dialog-tabHide'>
					this is step 3
				</div>
				<div id='step4' class='dialog-tabHide'>
					this is step 4
				</div>
			</form>
		</div>
</template>

<script>
	export default{
		name:'next',
		data(){
			return {
				current:'step1',
				isClick:true,
				num:12
			}
		},
		props:{
			navList:{
				default(){
					return [
						{name:'1 选择名称和位置',step:'#step1',active:true,getData:'getStepData'},
						{name:'2 添加主机',step:'#step2',active:false,checkFun:'check'},
						{name:'3 配置上行链路',step:'#step3',active:false},
						{name:'4 即将完成',step:'#step4',active:false,getData:'getStepData'},
					]
				}
			}
		},
		methods:{
			getStepData(){
				console.log(' this is getData')
			},
			check(){
				this.num++;
				if(this.num % 2 === 1){
				//	return false;
				}
				return true;
			},
			clickUl($event){
				this.$root.resetNavList([
					{name:'1 选择名称和位置',step:'#step1',active:true},
					{name:'2 添加主机',step:'#step2',active:false},
					{name:'3 配置上行链路',step:'#step3',active:false},
					
				])
			},
			complateFun(){

				this.$root.close();
			},
			cancelFun(){
				console.log('cancel');
			}
		},
	}
</script>
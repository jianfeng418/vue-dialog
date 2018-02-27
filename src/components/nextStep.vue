<template>
		<div>
			<form>
				<div id='step1' class=''>
					<p>this is step 1</p>
					<input v-model:value = 'num' type='text' /><br/><br/>
					<button @click='clickUl($event)' class='btn btn-default'>减少导航条目</button>
					<button @click='addNavItem()' class='btn btn-default'>增加导航条目</button>
					<input type='button' class='btn btn-default' @click='popup' value='弹出子框'>
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
	import test from './test.vue'
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
						{name:'1 step1',step:'#step1',active:true,getData:'getStepData'},
						{name:'2 step2',step:'#step2',active:false,checkFun:'check'},
						{name:'3 step3',step:'#step3',active:false},
						{name:'4 step4',step:'#step4',active:false,getData:'getStepData'},
					]
				}
			}
		},
		mounted(){
			
		},
		methods:{
			getStepData(){
				console.log(' this is getData')
			},
			check(){
				return true;
			},
			clickUl($event){
				this.$root.resetNavList([
					{name:'1 step1',step:'#step1',active:true},
					{name:'2 step2',step:'#step2',active:false},
					{name:'3 step3',step:'#step3',active:false},
					
				])
			},
			addNavItem(){
				this.$root.resetNavList([
					{name:'1 step1',step:'#step1',active:true},
					{name:'2 step2',step:'#step2',active:false},
					{name:'3 step3',step:'#step3',active:false},
					{name:'4 step4',step:'#step4',active:false,getData:'getStepData'},	
				])
			},
			popup(){
				 var that = this;
				 var dia = this.$v_dialog({
			          title:'创建账号',
			          width:'400px',
			          height:'300px',
			          multi:false,  //多步操作传true
			          render:test,
			          appData:{name:that.num,description:'good boy'},
			          complate:function(data){
			          		that.num = data
			          },
			      });  
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
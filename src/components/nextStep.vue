<template>
	<div class='next'>
		<div class='north'>
			<ul class="nav nav-tabs" @click='clickUl($event)'>
				<li v-for='item in navList' :class = '{active:item.active}'>
					<a @click.prevent :href='item.step'>{{item.name}}</a>
				</li>
			</ul>
		</div>
		<div>
			<form>
				<div id='step1' class=''>
					this is step 1
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

		<div></div>
		
	</div>
</template>

<script>
	export default{
		name:'next',
		data(){
			return {
				current:'step1',
				isClick:true,
				
			}
		},
		props:{
			navList:{
				default(){
				return [
					{name:'1 选择名称和位置',step:'#step1',active:true},
					{name:'2 添加主机',step:'#step2',active:false},
					{name:'3 配置上行链路',step:'#step3',active:false},
					{name:'4 即将完成',step:'#step4',active:false},
				
				]
				}
			},
		},
		methods:{
			click(){
				console.log(2)
			},
			clickUl($event){
				this.navList.forEach(function(li,index){
					if($event.target.getAttribute('href') === li.step){
						li.active = true;
					}else{
						li.active = false;
					}
					
				})
			}
		}
	}
</script>
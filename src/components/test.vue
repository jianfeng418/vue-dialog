<template>
	<div class=''>
		<form class="form-horizontal" role="form">
			<h5>设置属性</h5>
			<div class="form-group">
				<label for="lastname" class="col-sm-4 control-label">名称：</label>
				<div class="col-sm-8">
					<input type="text" class="form-control" id="lastname" v-model='appData.name'  placeholder="请输入名称">
				</div>
			</div>
			<div class="form-group">
				<label for="description" class="col-sm-4 control-label">描述：</label>
				<div class="col-sm-8">
					<textarea type="text" class="form-control" id="description"  style='resize:none'  placeholder="请输入描述"></textarea>
				</div>
			</div>
		</form>
	</div>
</template>
<script>
export default{
	name:'createNet',
	data(){
		return {
		}
	},
	props:{
		msg:{
			default(){
				return 3
			}
		},
		appData:{}
	},
	methods:{
		complateFun(){
			this.$emit('complate',this.appData.name);
			this.$root.close();
		},
		sendData(){
			return this.msg
		}
	}
}
</script>
<style>
	.form-horizontal .control-label{
		text-align:left
	}
</style>
<template>
	<div class=''>
		<form class="form-horizontal" role="form">
			<h5>设置网络属性</h5>
			<div class="form-group">
				<label for="lastname" class="col-sm-2 control-label">名称：</label>
				<div class="col-sm-10">
					<input type="text" class="form-control" id="lastname"   placeholder="请输入名称">
				</div>
			</div>
			<div class="form-group">
				<label for="" class="col-sm-2 control-label">描述：</label>
				<div class="col-sm-10">
					<textarea type="text" class="form-control" id="" style='resize:none'  placeholder="请输入描述"></textarea>
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
	}
}

</script>
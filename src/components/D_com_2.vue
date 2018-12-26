<template>
	<div>	
		<form>
			<h2>Employee Form</h2>
			<p>Name : <input type="text"></p>
			<p>Designation : <input type="text"></p>
			<p>Phone : <input type="text"></p>
			<p><button type="button">Save Employee</button></p>
		</form>

	</div>
</template>
<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			
		}
	}
</script>

<style scoped>
	h3{
		color: red;
		font-size: 30px;
		border-bottom: solid 2px red;
		padding-bottom: 20px;
 	}
 	form{
 		padding: 10px;
 		border: 2px solid green;
 	}
</style>
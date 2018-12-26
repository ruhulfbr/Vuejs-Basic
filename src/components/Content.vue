<template>
	<div>
		<h3>{{ content_title }}</h3>

		<div v-for="stu in students">
			<p><b>{{ stu.name }}</b></p>
		</div>

	</div>
</template>
<script>
	export default{
		// props:["students"],
		props:{
			students:{
				type:Array,
				required:true
			}
			
			
		},
		data(){
			return{
				content_title:"This is Content body"
			}
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
</style>
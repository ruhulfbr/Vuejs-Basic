<template>
	<div>
		<h3>{{ footer_title }}</h3>
	</div>
</template>
<script>
	export default{
		data (){
			return{
				footer_title:"This is Footer"
			}
		}
	}
</script>

<style scoped>
	h3{
		color: blue;
		font-size: 30px;
 	}
</style>
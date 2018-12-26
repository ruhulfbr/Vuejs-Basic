<template>
	<div>
		<h3>{{ header_title }}</h3>
	</div>
</template>
<script>
	export default{
		data(){
			return{
				header_title:"This is header"
			}
		}
	}
</script>

<style scoped>
	h3{
		color: green;
		font-size: 30px;
		border-bottom: solid 2px red;
 	}
</style>
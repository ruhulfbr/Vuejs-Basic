<template>
	<div>
		<p v-for="blog in blogs">
			<ul>
				<li>ID : {{blog.userId}}</li>
				<li>Title : {{blog.title}}</li>
				<li> Body : {{blog.body}}</li>
			</ul>
		</p>
	</div>
</template>

<script>
	export default{
		data (){
			return{
				blogs:[]
			}

		},
		methods:{

		},
		created(){
			this.$http.get("https://jsonplaceholder.typicode.com/posts").then(function(data){
				console.log(data);
				this.blogs = data.body.slice(0,5);

			});
		}
	}
</script>

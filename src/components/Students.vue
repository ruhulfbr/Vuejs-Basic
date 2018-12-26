<template>
	<div>	

		<form>
			<slot>This is slot default Message</slot>
			<div id="form-header">
				<slot name="form-header"></slot>
			</div>
			<div id="form-elements">
				<slot name="form-elements"></slot>
			</div>
			<div id="form-button">
				<slot name="form-button"></slot>
			</div>
			<div id="form-footer">
				<slot name="form-footer"></slot>
			</div>
		</form>

		<h2>Student List</h2>
		<h1>{{ message }}</h1>
		<button type="button" @click="updateMesage()">Change Data from Child</button>


		<div v-for="st in students">
			<p>{{st.name}}</p>
		</div>
		<button @click="deleteStudent()">Delete Students</button>

	</div>
</template>
<script>
	export default{
		// props:["students"],
		props:{
			students:{
				type:Array,
			},
			message:{
				type:String
			}
			
		},
		data(){
			return{
				content_title:"Student List"
			}
		},
		methods:{
			deleteStudent(){
				this.students.pop();
			},
			updateMesage(){
		      //this.message = "Update data From Child"
		      this.$emit("UpdateValueVariable","Update data From Child by emit");
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
 	form{
 		padding: 10px;
 		border: 2px solid green;
 	}
</style>
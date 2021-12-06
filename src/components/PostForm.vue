<template>
	<form @submit.prevent>
		<h4>Creating Post</h4>
		<input 
			v-model="post.title"
			class="input" 
			type="text" 
			placeholder="name"
		>
		<input 
			v-model="post.body"
			class="input" 
			type="text" 
			placeholder="desc"
		>
		<button 
			class="btn" 
			@click="createPost"
			>
			Create post
		</button>
	</form>
</template>

<script>
	export default {
		data(){
			return{
				post: {
					title: '',
					body: '',

				}
			}
		},
		methods: {
			createPost () {
				this.post.id = Date.now();
				this.$emit('create', this.post)
				this.post = {
					title : '',
					body : '',
				}
			}
		}
		
	}
</script>

<style lang="css" scoped>
form{
	display: inline-flex;
	flex-direction: column;
	border: 2px solid teal;
	padding: 15px;
	
}
.input {
	width: 350px;
	border: 2px solid teal;
	padding:  10px 15px;
	margin-top: 15px;
}
.btn {
	width: 220px;
	padding: 10px;
	margin-top: 25px;
	text-transform: uppercase;
	align-self: center;
	cursor: pointer;
}
</style>
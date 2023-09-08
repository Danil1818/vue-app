<template>
	<div class="app">
		<h1>Page with Posts</h1>
		<my-button 
			@click="showDialog"
			style="margin: 15px 0"
		>
			Create Post
		</my-button>
		<my-dialog v-model:show="dialogVisible">
			<post-form @create="createPost" />
		</my-dialog>
		<post-list :posts="posts" @remove="removePost" />
	</div>
</template>

<script>
	import PostForm from './components/PostForm.vue'
	import PostList from './components/PostList.vue'
	export default {
		components: {
			PostList,
			PostForm,
		},
		data() {
			return {
				posts: [
					{
						id: 1,
						title: 'HTML',
						body: 'Js is uneversal programming language!',
					},
					{
						id: 2,
						title: 'CSS',
						body: 'Js is uneversal programming language!',
					},
					{ id: 3, title: 'Js', body: 'Js is uneversal programming language!' },
				],
				dialogVisible: false,
			}
		},
		methods: {
			createPost(post) {
				this.posts.push(post)
				this.dialogVisible = false
			},
			removePost(post) {
				this.posts = this.posts.filter(p => p.id !== post.id)
			},
			showDialog() {
				this.dialogVisible = true
			},
		},
	}
</script>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;0,500;0,700;1,400&display=swap');
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}
	body {
		font-family: 'Montserrat', sans-serif;
		padding: 20px;
	}
	button,
	input,
	a {
		font-family: inherit;
		font-weight: inherit;
		color: inherit;
	}
</style>

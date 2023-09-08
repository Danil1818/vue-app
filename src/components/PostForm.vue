<template>
	<div>
		<form @submit.prevent>
			<h2>Create posts</h2>
			<my-input
				v-model="post.title"
				type="text"
				placeholder="Post name"
			/>
			<my-input
				v-model="post.body"
				type="text"
				placeholder="Post description"
			/>
			<my-button class="btn" style="align-self: flex-end" @click="createPost"
				>Add post
			</my-button>
		</form>
	</div>
</template>

<script>
export default {
	data() {
		return {
			post: {
				title: '',
				body: '',
			},
		}
	},
	methods: {
		createPost() {
			this.post.id = Date.now()
			this.$emit('create', this.post)
			this.post = {
				title: '',
				body: '',
			}
		},
	},
}
</script>

<style scoped>
form {
	display: flex;
	flex-direction: column;
	border-radius: 5px;
	margin-top: 15px;
}
</style>

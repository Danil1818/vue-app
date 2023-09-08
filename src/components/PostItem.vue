<template>
	<div class="post">
		<div>
			<p><strong>Name: </strong>{{ post.title }}</p>
			<p><strong>Description: </strong>{{ post.body }}</p>
		</div>
		<div class="post__bnts">
			<my-button @click="$emit('remove', post)">Delete</my-button>
		</div>
	</div>
</template>

<script>
	export default {
		props: {
			post: {
				type: Object,
				required: true,
			},
		},
	}
</script>

<style scoped>
	.post {
		padding: 15px;
		border: 2px solid rgb(6, 159, 255);
		margin-top: 15px;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.btn {
		border: 2px solid red;
		background-color: red;
		border-radius: 2px;
		color: #fff;
	}
	.btn:hover {
		background-color: #fff;
		color: red;
	}
</style>

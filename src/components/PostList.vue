<template>
	<div v-if="posts.length > 0">
		<h3>Users List</h3>
		<post-item
			v-for="post in posts"
			:post="post"
			:key="post.id"
			@remove="$emit('remove', post)"
		/>
	</div>
	<h2 v-else>
		Posts undefined :(
	</h2>
</template>

<script>
import PostItem from '@/components/PostItem.vue'
export default {
	components: { PostItem },
	props: {
		posts: {
			type: Array,
			required: true,
		},
	},
}
</script>

<style scoped></style>

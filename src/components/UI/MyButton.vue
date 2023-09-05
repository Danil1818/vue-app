<template>
	<button class="btn">
		<slot></slot>
	</button>
</template>

<script>
export default {
	name: 'my-button'
}
</script>

<style scoped>
.btn {
	border: 2px solid rgb(6, 159, 255);
	background-color: rgb(6, 159, 255);
	border-radius: 2px;
	padding: 5px 15px;
	font-weight: 500;
	cursor: pointer;
	transition: 0.3s;
}
.btn:hover {
	background-color: #fff;
	color: #000;
}
</style>

<template>
	<input :value='modelValue' @input='updateInput' class='input' type="text" />
</template>

<script>
export default {
	name: 'my-input',
	props: {
		modelValue: [String, Number]
	},
	methods: {
		updateInput(event) {
			this.$emit('update:modelValue', event.target.value)
		}
	},
}
</script>

<style scoped>
.input {
	width: 100%;
	border: 1px solid rgb(6, 159, 255);
	padding: 5px;
	margin: 5px 0;
}
</style>

<template>
	<div>{{ filteredTitle }}</div>
	<button @click="moveBitch(filteredTitle)">Move</button>
</template>

<script>
// import titles from '../post-data.json'
import { computed } from 'vue'
export default {
	props: {
		query: {
			type: String,
			default: '',
		},
		moveBitch: {
			required: true,
			type: Function,
		},
	},

	setup(props) {
		const filteredTitle = computed(() => {
			return props.query
		})
		return { filteredTitle }
	},
}
</script>

<style lang="scss" scoped></style>

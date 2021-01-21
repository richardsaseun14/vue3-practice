<template>
	<div class="hello">
		<h2>Filter LearnVue Articles</h2>
		<input v-model="query" type="text" placeholder="Filter Search" />
		{{ query }}
		<button @click="reset">Clear</button>

		<search-results :query="query" :move-bitch="naMethod"></search-results>
	</div>
</template>

<script>
import { ref } from 'vue'
import SearchResults from './SearchResults'
export default {
	components: {
		SearchResults,
	},

	setup() {
		const query = ref('')

		const reset = () => {
			console.log(query)
			query.value = ''
		}

		const naMethod = evt => {
			console.log(evt)
		}
		return { query, reset, naMethod }
	},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
	margin: 40px 0 0;
}
input {
	height: 24px;
}
</style>

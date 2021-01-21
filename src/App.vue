<template>
	<div id="nav">
		<router-link to="/">Home</router-link>
		|
		<router-link to="/about">About</router-link>
		<p>
			{{ x }}
			{{ y }}
			{{ isDark }}
			{{ store }}
		</p>
	</div>
	<router-view />
</template>

<script>
import { useMouse, usePreferredDark, useLocalStorage } from '@vueuse/core'

export default {
	setup() {
		// tracks mouse position
		const { x, y } = useMouse()

		// is user prefers dark theme
		const isDark = usePreferredDark()

		// persist state in localStorage
		const store = useLocalStorage('my-storage', {
			name: 'Apple',
			color: 'red',
		})

		return { x, y, isDark, store }
	},
}
</script>

<style lang="scss">
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
}

#nav {
	padding: 30px;

	a {
		font-weight: bold;
		color: #2c3e50;

		&.router-link-exact-active {
			color: #42b983;
		}
	}
}
</style>

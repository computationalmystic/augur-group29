<template>
  <button v-on:click="">Add Repository</button>
</template>

<script>
	export default {
		name: 'CompareRepos', 
		data() {
			return {
				isOpen: false
			}
		}, 
		methods: {
			addWhatever() {
				isOpen = true;
				return;
			}
		}
	}	
</script>

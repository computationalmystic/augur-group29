<template>
	<div id="repo-search-bar">
		<input v-if="isSearchBarOpen" type="text" v-model="msg" placeholder="search repo...">
		<button v-on:click="search">{{ computeButtonText }}</button>
	</div>
</template>

<script>
	export default {
		name: "RepoSearchBar",
		data() {
			return {
				isSearchBarOpen: false,
				msg: "floopynoopers"
			};
				
		},
		methods: {
			openSearchBar() {
				this.isSearchBarOpen = true;
			}, 
			search() {
				if (!isSearchBarOpen) {
					openSearchBar();
				}
				else{
					
				}
				// search using message...
			}


		}, 
		computed: {
			computeButtonText() {
				return this.isSearchBarOpen ? 'Submit' : 'Search Repo';
			}
		}
	}
</script>
<template>
	<div id="repo-search-bar">
		<transition name="zhoop">
			<input v-if="isSearchBarOpen" type="text" v-model="msg" placeholder="search repo...">
		</transition>
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
				if (!this.isSearchBarOpen) {
					this.openSearchBar();
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

<style scoped>
	.zhoop-enter-active, .zhoop-leave-active{
		transition: width 0.5s ease;
	}
	
	.zhoop-enter, .zhoop-leave-to{
		width: 0px;
	}

	.zhoop-leave, .zhoop-enter-to{
		width: 200px;
	}
</style>

<template>
	<div id="detail" v-if="movie">
		<movie-item v-bind:movie="movie.movie" v-bind:sessions="[]">
			<div class="movie-details">
				<p class="movie-genre">{{ movie.movie.Genre }}</p>
			</div>
		</movie-item>
	</div>
</template>
<script>
	import MovieItem from './MovieItem.vue'; 

	export default	{
		props: [ 'movies' ],
		computed: {
			movie() {
				let movie = this.movies.find(movie => movie.id === this.$route.params.id);
				return movie ? movie : null
			}
		},
		components: {
			MovieItem
		},
		created() {
			console.log(this.$route.params.id);
		}
	}
</script>
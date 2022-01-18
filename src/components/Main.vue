<template>
<main class="pb-6">
    <div class="container-60 py-4">
		<div class="row">
			<div class="col-4 offset-8">
				<label class="p-2" for="genre">Scegli un genere:</label>
				<Search @doSelect="cardsFilter($event)"/>
				<!-- <select v-model="genreSelect" name="genre" id="genre" class="form-select" @change="cardsFilter">
				<option value="all">All</option>
				<option value="rock">Rock</option>
				<option value="pop">Pop</option>
				<option value="jazz">Jazz</option>
				<option value="metal">Metal</option>
				</select> --> 
			</div>
		</div>
		<div v-if="selectedCards" class="row row-cols-5">
            <Card 
            v-for="(card, index) in selectedCards" :key="index" :image="card.poster" :name="card.title" :title="card.title" :artist="card.author" :year="card.year"/>
			<!-- <div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersey</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersey</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersey</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersey</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersey</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersey</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersey</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersey</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersey</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersey</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div> -->
		</div>
		<div v-else class="loading">
				<h1>Loading...</h1>
			</div>
	</div>
</main>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';
import Search from './Search.vue'
export default {
  name: "Main",
	components: {
		Card,
		Search,
	},
	data() {
		return {
			selectedCards: null,
			genreSelect: 'all',
			firstArray: null,
		}
	},
	mounted() {
		setTimeout(() => {
			this.getCards();
		}, 2000);
	},
	methods: {
		getCards () {
			axios.get('https://flynn.boolean.careers/exercises/api/array/music')
			.then((result) => {
				this.firstArray = result.data.response;
				this.selectedCards = result.data.response;
				
			})
			.catch((error) => {
				console.log(error);
			})
		},

	cardsFilter(text) {
			//di partenza si vedono tutti gli album
			this.selectedCards = this.firstArray;
			//selezione genere
			if (text !== 'all') {
				this.selectedCards = this.selectedCards.filter(album => album.genre.toLowerCase()  === text);
			} else {
				return this.selectedCards;
			}
		}
	}
}
</script>


<style lang="scss">
main {
    background-color: #1e2d3b;
	height:100vh;
}
label {
	color: white;
}
.container-60 {
	width: 60%;
	margin: auto;
	.col {
		padding: 0.5em 1em;
	}
	.loading {
		color: white;
		display: flex;
		justify-content: center;
	}
}
</style>


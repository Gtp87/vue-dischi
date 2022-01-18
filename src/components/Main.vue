<template>
<main>
     <div class="container-60 py-5">
		<div class="row">
			<div class="col-12">
				<label class="p-2" for="genre">Scegli un genere:</label>
				<select name="genre" id="genre">
				<option value="all">All</option>
				<option value="rock">Rock</option>
				<option value="pop">Pop</option>
				<option value="jazz">Jazz</option>
				<option value="metal">Metal</option>
				</select>
			</div>
		</div>
		<div class="row row-cols-5">
            <Card 
            v-for="(card, index) in cards" :key="index" :image="card.poster" :name="card.title" :title="card.title" :artist="card.author" :year="card.year"/>
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
	</div>
</main>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';
export default {
  name: "Main",
	components: {
		Card,
	},
	data() {
		return {
			cards: null,
		}
	},
	mounted() {
		this.getCards();
	},
	methods: {
		getCards() {
			axios.get('https://flynn.boolean.careers/exercises/api/array/music')
			.then((result) => {
				this.cards = result.data.response;
			})
			.catch((error) => {
				console.log(error);
			})
		}
	}
}
</script>


<style lang="scss">
main {
    background-color: #1e2d3b;
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
}
</style>


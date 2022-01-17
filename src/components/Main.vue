<template>
<main>
     <div class="container-60 py-5">
		<div class="row row-cols-5">
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersy</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersy</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersy</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersy</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersy</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersy</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersy</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersy</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersy</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
			<div class="col">
				<div class="spotify-card">
					<img class="p-3" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
					<span class="title">new jersy</span>
					<span class="subtitle">Bon Jovi</span>
					<span class="year">1988</span>
				</div>
			</div>
		</div>
	</div>
</main>
</template>

<script>
// import axios from 'axios';
export default {
  name: "Main",
}
</script>


<style lang="scss">
main {
    height: calc(100vh - 55px);
    background-color: #1e2d3b;
}
.container-60 {
	width: 60%;
	margin: auto;
	.col {
		padding: 0.5em 1em;
	}
	.spotify-card {
		background-color: #2E3A46;;
		display: flex;
		flex-direction: column;
		align-items: center;
		img {
			width: 100%;
		}
		.title {
			text-transform: uppercase;
			color: white;
			font-weight: 500;
		}
		.subtitle, .year {
			color: #5C6D78;
		}
	}
}
</style>


<template>
	<section class="single-recipe">
		<h1>{{ recipe.title }}</h1>
		<div>
			<img class="recipe-images" :src="recipe.thumbnail" :alt="recipe.title">
		</div>
		<p>{{ recipe.descriptionText }}</p>
	</section>
</template>

<script>

export default {
	asyncData(context) {
		return new Promise ((resolve, reject) => {
			setTimeout(() => {
				resolve({
					recipe: [
						{
							id: "1",
							title: "Delicious pizza",
							previewText: "Awesome Pizza",
							descriptionText: "This is really a delicious meal!",
							thumbnail: "https://www.patee.ru/r/x6/11/11/90/640m.jpg"
						},
						{
							id: "2",
							title: "Delicious salad",
							previewText: "Very tasty indeed!",
							descriptionText: "This is really a delicious meal!",
							thumbnail: "http://italianmeal.domestic-travel.ru/wp-content/uploads/sites/11/2016/10/salat_parmigiano.jpg"
						}

					].find(el => el.id === context.params.id)
				})
			},1500)
		})
	}

}

</script>

<style scoped>
.single-recipe{
	display: flex;
	flex-flow: column;
	justify-content: center;
	align-items: center;
	text-align: center;
	padding: 30px;
}
.recipe-images {
	width: 100%;
}
</style>
<template>
	<section class="recipes">
		<Recipe 
		v-for="recipe in recipes"
		:key="recipe.id"
		:thumbnail="recipe.thumbnail"
		:title="recipe.title" 
		:id="recipe.id"
		:previewText="recipe.previewText" />
	</section>
</template>

<script>
import Recipe from '@/components/Recipe';
export default{
	components: {
		Recipe
	},
	asyncData() {
		return new Promise ((resolve, reject) => {
			setTimeout(() => {
				resolve({
					recipes: [
						{
							id: "1",
							title: "Delicious pizza",
							previewText: "Awesome Pizza",
							thumbnail: "https://www.patee.ru/r/x6/11/11/90/640m.jpg"
						},
						{
							id: "2",
							title: "Delicious salad",
							previewText: "Very tasty indeed!",
							thumbnail: "http://italianmeal.domestic-travel.ru/wp-content/uploads/sites/11/2016/10/salat_parmigiano.jpg"
						}

					]
				})
			},1500)
		})
	}
};
</script>

<style scoped>
.recipes {
	display: flex;
	flex-flow: row wrap;
	justify-content: center;
	align-items: center;
}


</style>
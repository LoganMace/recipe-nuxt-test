<template>
  <section class="single_recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe_image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{ recipe.descriptionText }}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    // Faking an async request from a server. Nuxt will wait for the resolve and then merge into the existing data object.
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "One Pot Spaghetti",
              previewText: "Delicious Pasta!",
              thumbnail: "https://ichef.bbci.co.uk/food/ic/food_16x9_832/recipes/one_pot_chorizo_and_15611_16x9.jpg",
              descriptionText: "This is the full description."
            },
            {
              id: "2",
              title: "Sweet and Sour Pork",
              previewText: "Delicious Pork!",
              thumbnail: "https://timedotcom.files.wordpress.com/2015/02/155278138-copy.jpg",
              descriptionText: "This is the full description."
            }
          ].find((recipe) => recipe.id === context.params.id)
        })
      }, 1500)
    })
  }
}
</script>


<style scoped>
  .single_recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
  }
  .recipe_image {
    width: 500px;
    height: auto;
  }
</style>
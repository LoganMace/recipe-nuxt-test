<template>
  <section class="recipes">
    <Recipe 
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :previewText="recipe.previewText"
      :id="recipe.id"
    />
  </section>
</template>

<script>
import Recipe from '@/components/Recipe';
export default {
  components: {
    Recipe
  },
  asyncData() {
    // Faking an async request from a server. Nuxt will wait for the resolve and then merge into the existing data object.
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "One Pot Spaghetti",
              previewText: "Delicious Pasta!",
              thumbnail: "https://ichef.bbci.co.uk/food/ic/food_16x9_832/recipes/one_pot_chorizo_and_15611_16x9.jpg"
            },
            {
              id: "2",
              title: "Sweet and Sour Pork",
              previewText: "Delicious Pork!",
              thumbnail: "https://timedotcom.files.wordpress.com/2015/02/155278138-copy.jpg"
            }
          ]
        })
      }, 1500)
    })
  }
}
</script>


<style scoped>
  .recipes {
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
  }
</style>

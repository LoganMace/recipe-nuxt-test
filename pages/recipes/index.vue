<template>
  <section class="recipes">
    <Recipe 
      thumbnail="https://ichef.bbci.co.uk/food/ic/food_16x9_832/recipes/one_pot_chorizo_and_15611_16x9.jpg"
      title="One Pot Spaghetti"
      previewText="Delicious Pasta!"
    />
    <Recipe 
      thumbnail="https://timedotcom.files.wordpress.com/2015/02/155278138-copy.jpg"
      title="Sweet and Sour Pork"
      previewText="Delicious Pork!"
    />
  </section>
</template>

<script>
import Recipe from '@/components/Recipe';
export default {
  components: {
    Recipe
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

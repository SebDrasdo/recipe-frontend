<template>
  <h1>Welcome to Recipes</h1>
  <div class="container-fluid">
    <div class="row row-cols-1 row-cols-md-2 g-4">
      <div class="col" v-for="recipe in recipes" :key="recipe.recipeName">
        <div class="card">
          <img src="../assets/kaninchenv2.png" class="card-img-top" alt='recipe.recipeName'>
          <div class="card-body">
            <h5 class="card-title">{{ recipe.Name }}</h5>
            <p class="card-text">
              Anleitung: {{recipe.description}}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Recipes',
  data () {
    return {
      recipes: [
        {
          id: 1,
          recipeName: 'Quatsch mit Sauce',
          description: 'alles nicht so schwer',
          vegan: true
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>

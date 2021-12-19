<template>
  <h1>Welcome to Recipes</h1>
  <div class="container-fluid">
    <div class="row row-cols-1 row-cols-md-2 g-4">
      <div class="col" v-for="recipe in recipes" :key="recipe.id">
        <div class="card h-100">
          <img src="../assets/kaninchenv2.png" class="card-img-top" alt='recipe.recipeName'>
          <div class="card-body">
            <h5 class="card-title">{{ recipe.recipeName }}</h5>
            <p class="card-text">
              {{ recipe.description }}
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
      recipes: []
    }
  },
  mounted () {
    const endpoint = process.env.VUE_APP_BACKEND_BASE_URL + '/api/v1/recipes'
    const requestOptions = {
      method: 'GET',
      redirect: 'follow'
    }
    fetch(endpoint, requestOptions)
      .then(response => response.json())
      .then(result => result.forEach(recipe => {
        this.recipes.push(recipe)
      }))
      .catch(error => console.log('error', error))
  }
}
</script>
<style scoped>
</style>

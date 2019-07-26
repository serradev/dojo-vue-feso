<template>
  <div> 
    <div class="card">
      <nav aria-label="breadcrumb">
        <ol class="breadcrumb">
            <li class="breadcrumb-item"><a href="#">Home</a></li>
            <li class="breadcrumb-item"><a href="#">Library</a></li>
            <li class="breadcrumb-item active" aria-current="page">Data</li>
        </ol>
      </nav>     
      <img src="../assets/pokedex.png" class="card-img-top">
    </div>
  </div>
</template>

<script>
export default {
  name: 'PokemonCard',
  props: {
    item: String
  }
}
</script>

<style>
</style>
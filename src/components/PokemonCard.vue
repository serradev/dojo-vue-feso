<template>
  <div> 
    <div class="card">
      <nav aria-label="breadcrumb">
        <ol class="breadcrumb mb-0">
            <li class="breadcrumb-item"><a href="#">Home</a></li>
            <li class="breadcrumb-item"><a href="#">Library</a></li>
            <li class="breadcrumb-item active" aria-current="page">Data</li>
        </ol>
      </nav>     
      

      <div class="card-body">
        <img src="../assets/pokedex.png" class="card-img-top mt-0 mb-2">
        <PokemonStat></PokemonStat>
      </div>
    </div>
  </div>
</template>

<script>
import PokemonStat from "../components/PokemonStat.vue";
export default {
  name: 'PokemonCard',
  components: {
    PokemonStat
  },
  props: {
    item: String
  }
}
</script>

<style>
</style>
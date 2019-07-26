<template>
  <body>
    <div id="app" class="container">  
      <nav class="d-flex justify-content-center mb-5 pt-0">
        <img alt="Pokedex" src="./assets/pokedex.png" />  
      </nav>
      <div class="col-12 row">
        <aside class="col-5">
          <PokemonList @pokemon-selecionado="pokemonAlterado"></PokemonList>
        </aside> 
        <div class="col-7">
          <PokemonCard :item="pokemonSelecionado"></PokemonCard>
        </div>           
      </div>
    </div>
  </body>
</template>

<script>
import PokemonList from "./components/PokemonList.vue";
import PokemonCard from "./components/PokemonCard.vue";

export default {
  name: "app",
  components: {
    PokemonList,
    PokemonCard
  },
  data() {
    return {
      pokemonSelecionado: undefined
    }
  },
  methods: {
    pokemonAlterado(e) {
      this.pokemonSelecionado = e;
    }
  }
};
</script>

<style>
  @import '../node_modules/bootstrap/dist/css/bootstrap.css';

  body {
    background:url(https://images8.alphacoders.com/558/558665.jpg) no-repeat !important;
    background-size:cover;
    margin-bottom: 20px;
  }
</style>

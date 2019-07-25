<template>
  <body>
    <container id="app" class="container">  
      <nav class="d-flex justify-content-center mb-5 pt-0">
        <img alt="Pokedex" src="./assets/pokedex.png" />  
      </nav>
      <aside class="col-5">
        <PokemonList titulo="Pokemons"/>
      </aside>      
    </container>
  </body>
</template>

<script>
import PokemonList from "./components/PokemonList.vue";

export default {
  name: "app",
  components: {
    PokemonList
  }
};
</script>

<style>
  @import '../node_modules/bootstrap/dist/css/bootstrap.css';

  body {
    background:url(https://images8.alphacoders.com/558/558665.jpg) no-repeat !important;
    background-size:cover;
  }
</style>

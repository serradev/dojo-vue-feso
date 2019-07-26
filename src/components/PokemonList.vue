<template>
  <div class="list-group">
    <button  v-for="p in pokemons" :key="p.order" type="button" class="list-group-item list-group-item-action">
      {{p.name}}
    </button>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'pokemonList',
  props: {
    titulo: String
  },
  data: function() {
    return {
      pokemons: []
    }    
  },  
  methods: {
    obterListaPokemon(offset) {
      const URL = 'https://pokeapi.co/api/v2/pokemon/';
      return axios
        .get(URL, {
          params: {
            offset,
            limit: 20
          }
        })
        .then(response => {
          let data = response.data.results;
          let retorno = [];
          data.forEach(item => {
            let pokemon = {
              name: item.name,
              order: parseInt(item.url.match(/[^/]+(?=\/$)/g)[0])
            };

            this.pokemons.push(pokemon);
          });
        })
    }
  },
  mounted() {
    this.obterListaPokemon(0);
  }
};
</script>

<style>
</style>
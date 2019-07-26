<template>
  <div class="list-group">
    <button  v-for="p in pokemons" :key="p.order" type="button" class="list-group-item list-group-item-action" v-on:click="obterDadosPokemon(p)">
      {{p.order}} - {{p.name}}
    </button>

    {{pokemonSelecionado}}
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
      pokemons: [],
      pokemonSelecionado: null
    }    
  },  
  methods: {
    obterDadosPokemon(pokemon) {
      return axios
        .get(pokemon.url)
        .then(response => {
          let data = response.data;
          let pokemonStats = [];
          data.stats.forEach(stat => {
            pokemonStats.push({
              baseStat: stat.base_stat,
              name: stat.stat.name,
              effort: stat.effort
            });
          });

          this.pokemonSelecionado = {
            name: data.name,
            order: data.order,
            stats: pokemonStats,
            image: data.sprites.front_default,
            type: data.types[0].type.name
          };
        });
    },
    carregarPokemons(pagina) {
      const URL = 'https://pokeapi.co/api/v2/pokemon/';
      return axios
        .get(URL, {
          params: {
            offset: pagina,
            limit: 20
          }
        })
        .then(response => {
          let data = response.data.results;
          data.forEach(item => {
            let pokemon = {
              name: item.name,
              order: parseInt(item.url.match(/[^/]+(?=\/$)/g)[0]),
              url: item.url
            };

            this.pokemons.push(pokemon);
          });

          
          return this.pokemons;
        })
    }
  },
  mounted() {
    this.carregarPokemons(0);
  }
};
</script>

<style>
</style>
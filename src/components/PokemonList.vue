<template>
  <div class="list-group">
    <button type="button" class="list-group-item list-group-item-action">
      Cras justo odio
    </button>
    <button type="button" class="list-group-item list-group-item-action">Dapibus ac facilisis in</button>
    <button type="button" class="list-group-item list-group-item-action">Morbi leo risus</button>
    <button type="button" class="list-group-item list-group-item-action">Porta ac consectetur ac</button>
    <button type="button" class="list-group-item list-group-item-action" disabled>Vestibulum at eros</button>

    {{pokemons}}


    <ul id="example-1">
      <li v-for="p in pokemons" :key="p.order">
        {{ p.name }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'pokemonList',
  props: {
    titulo: String
  },
  data() {
    this.pokemons = [];
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
    this.obterListaPokemon(0).then(
      data => {
        // POR QUE NÃO PRINTA NA TELA? O ARRAY TÁ PREENCHIDO!
        console.log(this.pokemons);
      }
    );    
  }
};
</script>

<style>
</style>
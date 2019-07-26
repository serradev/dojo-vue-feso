<template>
  <div>
    <h5 class="card-title">Stats</h5>

    <div class="list-group">
      <button type="button" class="list-group-item list-group-item-action" v-for="stat in item.stats" :key="stat.baseStat">
        {{stat.baseStat}} - {{stat.name}}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PokemonStat',
  props: {
    item: Object
  }
}
</script>

<style>
</style>
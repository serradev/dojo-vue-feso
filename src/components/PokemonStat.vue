<template>
  <div>
    <h5 class="card-title">Stats</h5>

    <div class="list-group">
      <button type="button" class="list-group-item list-group-item-action">Cras justo odio</button>
      <button type="button" class="list-group-item list-group-item-action">Dapibus ac facilisis in</button>
      <button type="button" class="list-group-item list-group-item-action">Morbi leo risus</button>
      <button type="button" class="list-group-item list-group-item-action">Porta ac consectetur ac</button>
      <button type="button" class="list-group-item list-group-item-action" disabled>Vestibulum at eros</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PokemonStat',
  props: {
    id: String
  }
}
</script>

<style>
</style>
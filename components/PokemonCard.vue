<template>
  <nuxt-link :to="'/' + pokemon.name">
    <div class="container">
      <h1>{{ pokemon.name }}</h1>
      <small># {{ pokemon.id }}</small>
      <div>
        <img :src="pokemon.sprite" :alt="'Picture of ' + pokemon.name" />
      </div>
      <p>Weight: {{ pokemon.weight }}</p>
      <p>Height: {{ pokemon.height }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    pokemon: {
      type: Object,
      default() {
        return { error: 'No Pokemon Recieved to PokemonCard Component' }
      },
    },
  },
}
</script>

<style scoped>
.container {
  width: 150px;
  height: 250px;
  background-color: whitesmoke;
  border: black 1px solid;
  margin: 5px;
  padding: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 8px;
}

.container:hover {
  background-color: rgb(230, 230, 230);
  cursor: pointer;
}
</style>

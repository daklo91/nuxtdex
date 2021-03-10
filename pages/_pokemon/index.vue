<template>
  <div>
    <!-- <button @click.prevent="consoleLog">Console Log</button> -->
    <div class="container" @click="handleBack">
      <h1>{{ pokemon.name }}</h1>
      <small># {{ pokemon.id }}</small>
      <div>
        <img :src="pokemon.sprite" :alt="'Picture of ' + pokemon.name" />
      </div>
      <p>Weight: {{ pokemon.weight }}</p>
      <p>Height: {{ pokemon.height }}</p>
    </div>
  </div>
</template>

<script>
import pokemonArray from 'assets/pokemonArray.json'

export default {
  data() {
    return {
      pokemon: '',
    }
  },
  created() {
    this.pokemon = pokemonArray.find((obj) => {
      return obj.name === this.$route.params.pokemon
    })
  },
  methods: {
    // consoleLog() {
    //   console.log(this.$router.history)
    // },
    handleBack() {
      // if (!this.fromRoute.name) {
      //   this.$router.push(fallback)
      // } else {
      if (this.$router.history._startLocation === '/') {
        this.$router.back()
      } else {
        this.$router.replace('/')
      }
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

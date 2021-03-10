<template>
  <div class="container">
    <!-- <button @click.prevent="consoleLog">Console Log</button> -->
    <div v-for="pokemon in pokemons" :key="pokemon.id">
      <PokemonCard :pokemon="pokemon" />
    </div>
  </div>
</template>

<script>
import pokemonArray from '@/assets/pokemonArray.json'
import PokemonCard from '@/components/PokemonCard.vue'

export default {
  components: {
    PokemonCard,
  },
  transition: 'home',
  data() {
    return {
      pokemons: pokemonArray,
    }
  },
  head: {
    title: 'NuxtDex',
    meta: [
      {
        hid: 'main-description',
        name: 'description',
        content:
          'NuxtDex the Pokedex made with Nuxt! Browse all of the 151 original pokemon in their glory!',
      },
    ],
  },
  methods: {
    consoleLog() {
      // eslint-disable-next-line no-console
      console.log(this.pokemons)
    },
  },
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

.home-enter-active,
.home-leave-active {
  transition: opacity 0.2s;
}
.home-enter,
.home-leave-active {
  opacity: 0;
}

.container {
  display: flex;
  flex-wrap: wrap;
}
</style>

<template>
  <div class="container text-center mt-5">
    <img
      src="/src/assets/pokemon-logo.png"
      alt="Logo Pokémon"
      class="img-fluid"
      width="400"
    />
    <h1>¿Quién es ese Pokémon?</h1>
    <h2>Pokémon descubiertos:</h2>
    <h3 id="contador">{{ contadorPokemonesDescubiertos }}</h3>

    <div class="row row-cols-1 row-cols-md-3 g-4">
      <PokemonCard
        v-for="pokemon in pokemones"
        :key="pokemon.id"
        :pokemon="pokemon"
        @descubierto="manejarDescubrimiento"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import PokemonCard from "./components/PokemonCard.vue";

export default {
  data() {
    return {
      pokemones: [],
    };
  },
  components: {
    PokemonCard,
  },
  computed: {
    contadorPokemonesDescubiertos() {
      return this.pokemones.filter(pokemon => pokemon.descubierto).length;
    }
  },
  methods: {
    obtenerPokemones() {
      axios.get("https://pokeapi.co/api/v2/pokemon?limit=20").then((response) => {
        const listaPokemones = response.data.results;
        this.pokemones = listaPokemones.map((pokemon, index) => ({
          nombre: pokemon.name,
          urlImagen: `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${index + 1}.png`,
          descubierto: false,
          id: index + 1,
        }));
      });
    },
  },
  mounted() {
    this.obtenerPokemones();
  },
};
</script>

<style scoped>
h1 {
  margin-top: 20px;
}

h3 {
  margin-bottom: 30px;
}

#contador {
  color: #fde400;
  animation: neonefecto 1s infinite;
}

/* Neon effect keyframes */
@keyframes neonefecto {
  0%, 100% {
    text-shadow: 0 0 5px #2E4594, 0 0 10px #2E4594, 0 0 20px #2E4594;
  }
  50% {
    text-shadow: 0 0 10px #2E4594, 0 0 20px #2E4594, 0 0 30px #2E4594;
  }
}

.card {
  height: 100%;
}
</style>

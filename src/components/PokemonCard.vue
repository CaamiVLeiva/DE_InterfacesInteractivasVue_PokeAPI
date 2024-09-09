<template>
    <div class="col-12 col-md-6 col-lg-4 mb-4">
        <div class="card">
            <img :src="pokemon.urlImagen" :class="{ 'filtro-borrado': !pokemon.descubierto }" class="card-img-top"
                alt="pokémon" />
            <div class="card-body">
                <h5 v-if="pokemon.descubierto" class="card-title">{{ pokemon.nombre }}</h5>
                <div v-else>
                    <input v-model="entradaUsuario" @keyup.enter="verificarNombre" class="form-control" type="text"
                        placeholder="¿Quién es?" />
                    <button @click="verificarNombre" class="btn btn-primary mt-2">
                        Descubrir
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        pokemon: Object,
    },
    data() {
        return {
            entradaUsuario: "",
        };
    },
    methods: {
        verificarNombre() {
            if (this.entradaUsuario.toLowerCase() === this.pokemon.nombre.toLowerCase()) {
                // eslint-disable-next-line vue/no-mutating-props
                this.pokemon.descubierto = true;
                this.$emit("descubierto");
            } else {
                alert("Nombre incorrecto, intenta de nuevo.");
            }
        },
    },
};
</script>

<style scoped>
.filtro-borrado {
    filter: blur(5px) grayscale(100%);
}

.card {
    height: 100%;
}
</style>
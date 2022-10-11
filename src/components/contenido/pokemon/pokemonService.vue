<script>
import ListaPokemones from './listaPokemones.vue';

export default {
    data() {
        return {
            personaje: {},
        };
    },
    props: {
        id: {
            type: Number
        },
    },
    emits: ["obtenerPersonaje"],
    methods: {
        buscarPersonaje(id) {
            fetch("https://pokeapi.co/api/v2/pokemon/" + id)
                .then(response => response.json())
                .then(data => {
                    this.personaje.name = data.name;
                    this.personaje.height = data.height,
                        this.personaje.weight = data.weight,
                        this.personaje.tipoPrincipal = data.types[0].type.name
                });
        }
    },
    components: { ListaPokemones }
}
</script>
        
<template>
    {{buscarPersonaje(id)}}
</template>
<script>
import Lista from '../lista.vue';

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
        url: {
            type: String
        },
    },
    emits: ["obtenerPersonaje"],
    methods: {
        buscarPersonaje(url, id) {
            fetch(url + id)
                .then(response => response.json())
                .then(data => {
                    this.personaje.name = data.name;
                    this.personaje.height = data.height,
                        this.personaje.weight = data.weight,
                        this.personaje.tipoPrincipal = data.types[0].type.name
                });
        }
    },
    components: { Lista }
}
</script>
        
<template>
    {{buscarPersonaje(url, id)}}
</template>
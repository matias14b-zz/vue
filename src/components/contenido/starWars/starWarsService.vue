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
    methods: {
        buscarPersonaje(url, id) {
            fetch(url + id)
                .then(response => response.json())
                .then(data => {
                this.personaje.name = data.name;
                this.personaje.height = data.height,
                    this.personaje.mass = data.mass,
                    this.personaje.hairColor = data.hair_color,
                    this.personaje.skinColor = data.skin_color,
                    this.personaje.eyeColor = data.eye_color,
                    this.personaje.birthYear = data.birth_year,
                    this.personaje.gender = data.gender;
            });
        },
    },
    components: { Lista }
}
</script>
    
<template>
        {{buscarPersonaje(url, id)}}
    <Lista :lista="this.personaje" />
</template>
<script>

export default {
    data() {
        return {

        }
    },
    props: {
        id: {
            type: Number
        },
    },
    personaje: {
        name: null,
        height: null,
        mass: null,
        hairColor: null,
        skinColor: null,
        eyeColor: null,
        birthYear: null,
        gender: null
    },
    emits: ['obtenerPersonaje'],
    methods: {
        async buscarPersonaje(id) {
            await fetch(`https://swapi.dev/api/people/${id}`)
                .then(response => response.json())
                .then(data => {
                    this.$options.personaje.name = data.name;
                    this.$options.personaje.height = data.height,
                        this.$options.personaje.mass = data.mass,
                        this.$options.personaje.hairColor = data.hair_color,
                        this.$options.personaje.skinColor = data.skin_color,
                        this.$options.personaje.eyeColor = data.eye_color,
                        this.$options.personaje.birthYear = data.birth_year,
                        this.$options.personaje.gender = data.gender
                });
        },
        sendData() {
            this.$emit('obtenerPersonaje', this.$options.personaje)
        }
    },
}
</script>
    
<template>
    <span>
        {{sendData()}}
        {{buscarPersonaje(id)}}
    </span>
</template>
<script>

export default {
    data() {
        return {
            jedi: {
                name: null,
                height: null,
                mass: null,
                hairColor: null,
                skinColor: null,
                eyeColor: null,
                birthYear: null,
                gender: null
            },
        }
    },
    props: {
        id: {
            type: Number
        }
    },
    emits: ['obtenerPersonaje'],
    methods: {
        buscarPersonaje(id) {
            fetch(`https://swapi.dev/api/people/${id}`)
                .then(response => response.json())
                .then(data => {
                    this.jedi.name = data.name;
                    this.jedi.height = data.height,
                        this.jedi.mass = data.mass,
                        this.jedi.hairColor = data.hair_color,
                        this.jedi.skinColor = data.skin_color,
                        this.jedi.eyeColor = data.eye_color,
                        this.jedi.birthYear = data.birth_year,
                        this.jedi.gender = data.gender
                });
        },
        sendData() {
            this.$emit('obtenerPersonaje',this.jedi)
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
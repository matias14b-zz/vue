<script>
import PokemonService from '../contenido/pokemon/pokemonService.vue';
import StarWarsService from '../contenido/starWars/starWarsService.vue';
export default {
    data() {
        return {
            elementosBuscados: [],
            pokemonesBuscados: [],
            mostrarInformacion: false
        };
    },
    methods: {
        obtenerId() {
            let id = document.querySelector(".id").value;
            let url = document.querySelector(".url").value;
            if (url === 'https://pokeapi.co/api/v2/pokemon/') {
                this.pokemonesBuscados.push({ id: id, url: url });
            }
            if (url === 'https://swapi.dev/api/people/') {
                this.elementosBuscados.push({ id: id, url: url });
            }
        },
        mostrarInformacion() {
            this.mostrarInformacion = !this.mostrarInformacion;
        }
    },
    components: {PokemonService, StarWarsService }
}
</script>
<template>
    <header class="py-3 mb-3 border-bottom bg-dark text-white">
        <div class="container-fluid ">
            <div class="d-flex flex-row align-items-center me-3 ">
                <div class="w-100">
                    <select class="url form-select">
                        <option value="https://swapi.dev/api/people/">star-wars</option>
                        <option value="https://pokeapi.co/api/v2/pokemon/">pokemon</option>
                    </select>
                </div>
                <div class="w-100">
                    <input type="text" class="id form-control">
                </div>
                <div class="p-2">
                    <button class="btn btn-primary" @click="obtenerId">Buscar Personaje</button>
                </div>
            </div>
        </div>
    </header>
    <!--  -->

    <div>
        <div id="carouselExampleFade" class="carousel carousel-dark slide" data-bs-ride="carousel">
            <div class="carousel-inner">
                <div class="d-flex me-3 justify-content-center">
                    <div class="carousel-inner w-75 ">
                        <div class="card bg-dark carousel-item active">
                            <div class="card-body">
                                <div>
                                    <StarWarsService class="d-block w-100" url='https://swapi.dev/api/people/' :id="1"></StarWarsService>
                                </div>
                            </div>
                        </div>
                        <div class="card bg-dark carousel-item" v-for="elemento in elementosBuscados"
                            :key="elemento.id">
                            <div class="card-body">
                                <div>
                                    <div>
                                        <StarWarsService class="d-block w-100" :url='elemento.url' :id="elemento.id"></StarWarsService>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="card bg-dark carousel-item" v-for="elemento in pokemonesBuscados"
                            :key="elemento.id">
                            <div class="card-body">
                                <div>
                                    <div>
                                        <PokemonService class="d-block w-100" :url='elemento.url' :id="elemento.id"></PokemonService>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleFade"
                    data-bs-slide="prev">
                    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Previous</span>
                </button>
                <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleFade"
                    data-bs-slide="next">
                    <span class="carousel-control-next-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Next</span>
                </button>
            </div>
        </div>
    </div>
</template>
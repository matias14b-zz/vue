<script>
import Card from '../contenido/cardPersonaje/card.vue';
import Dolar from '../contenido/dolar.vue';
export default {
    data() {
        return {
            idElementosBuscados: [],
            mostrarInformacion: false
        };
    },
    methods: {
        obtenerId() {
            let textoInput = document.querySelector(".textoInput").value;
            this.idElementosBuscados.push({ id: textoInput });
        },
        mostrarInformacion() {
            this.mostrarInformacion = !this.mostrarInformacion;
        }
    },
    components: { Card, Dolar }
}
</script>
<template>
    <header class="py-3 mb-3 border-bottom bg-dark text-white">
        <div class="container-fluid ">
            <div class="d-flex flex-row align-items-center me-3 ">
                <div class="w-100">
                    <input type="text" class="textoInput form-control">
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
                                    <Card class="d-block w-100" :id="1"></Card>
                                </div>
                            </div>
                        </div>
                        <div class="card bg-dark carousel-item" v-for="idElemento in idElementosBuscados"
                            :key="idElemento.id">
                            <div class="card-body">
                                <div>
                                    <div>
                                        <Card class="d-block w-100" :id="idElemento.id"></Card>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div v-if="mostrarInformacion" class="card bg-dark carousel-item">
                            <div class="card-body">
                                <div>
                                    <div>
                                         
                                         <dolar class="d-block w-100"></dolar>

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

    <footer class="py-3 mb-3 border-bottom bg-dark text-white">
        <div class="container-fluid ">
            <div class="d-flex flex-row align-items-center me-3 ">
                <div class="w-100">
                    <input type="text" class="textoInput form-control">
                </div>
                <div class="p-2">
                    <button class="btn btn-primary" @click="mostrarInformacion">Buscar Personaje</button>
                </div>
            </div>
        </div>
    </footer>
</template>
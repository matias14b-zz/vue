<script>
import ComponentePersonaje from '../ListaPersonaje/ComponentePersonaje.vue';
export default {
    data() {
        return {
            idElementosBuscados: []
        };
    },
    components: { ComponentePersonaje },
    methods: {
        obtenerId() {
            let textoInput = document.querySelector(".textoInput").value;
            this.idElementosBuscados.push({ id: textoInput });
        },
    }
}
</script>
<template>

    <header class="py-3 mb-3 border-bottom">
        <div class="container-fluid">

            <div class="d-flex flex-row align-items-center me-3 ">
                <div class="w-100">
                    <input type="text" class="textoInput form-control">
                </div>
                <div>
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
                                    <ComponentePersonaje class="d-block w-100" :id="1"></ComponentePersonaje>
                                </div>
                            </div>
                        </div>
                        <div class="card bg-dark carousel-item" v-for="idElemento in idElementosBuscados"
                            :key="idElemento.id">
                            <div class="card-body">
                                <div>
                                    <div>
                                        <ComponentePersonaje class="d-block w-100" :id="idElemento.id">
                                        </ComponentePersonaje>
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
<script setup>
import { ref } from 'vue';
const modalOpen = ref(false);

const closeModal = () => {
    modalOpen.value = false;
}

const showModal = () => {
    modalOpen.value = true;
}

</script>

<template>
    <section id="wishlist">
        <div class="container text-center mb-5">
            <div class="row">
                <div class="col-md-12">
                    <h2 class="heart section-header mb-0"><i class="fa-solid fa-heart fa-beat" style="color: #9337be;"></i>
                    </h2>
                    <h2 class="gift-text">Regalos</h2>
                    <div class="col-md-12">
                        <p class="p-2">Tu presencia es nuestro mejor regalo, pero si quieres tener un detalle con nosotros,
                            te damos
                            algunas sugerencias:</p>
                    </div>
                </div>
            </div>
            <div class="row mt-4">
                <div class="col-md-4">
                    <a href="https://mesaderegalos.liverpool.com.mx/milistaderegalos/51286518" target="_blank" class="card">
                        <div class="card-body">
                            <div class="row">
                                <div class="col-2 logo-wishlist">
                                    <img class="img-wishlist"
                                        src="https://yt3.googleusercontent.com/5Hq3_j7plTY_bWbwdjZ7uQhe8e_jjFUr1svIR_1j4Wcua8kb8ZxUdY-6daMVZFfF6xBPQAmy3g=s900-c-k-c0x00ffffff-no-rj"
                                        alt="Liverpool">
                                </div>
                                <div class="col-10">
                                    <p class="wishlist-link">Liverpool</p>
                                </div>
                            </div>
                        </div>
                    </a>
                </div>
                <div class="col-md-4">
                    <a target="_blank" href="https://www.sears.com.mx/Mesa-de-Regalos/96996/boda" class="card">
                        <div class="card-body">
                            <div class="row">
                                <div class="col-2 logo-wishlist">
                                    <img class="img-wishlist" src="https://cdn.lovesavingsgroup.com/logos/sears-mx.jpg"
                                        alt="Liverpool">
                                </div>
                                <div class="col-10">
                                    <p class="wishlist-link">Sears</p>
                                </div>
                            </div>
                        </div>
                    </a>
                </div>
                <div class="col-md-4">
                    <div @click="showModal" class="card" id="bank">
                        <div class="card-body">
                            <div class="row">
                                <div class="col-2 logo-wishlist">
                                    <i class="fa fa-money fa-2xl" style="color: #34a259;"></i>
                                </div>
                                <div class="col-10">
                                    <button class="btn wishlist-link">Datos bancarios</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div v-if="modalOpen" class="bank-data">
            <div class="modal-wishlist-content">
                <p class="text-center large-text mb-3">Datos Bancarios</p>
                <p>Rodríguez González Jair</p>
                <p>CLABE: 044420256032514145</p>
                <p>Banco: <img src="https://cdn.icon-icons.com/icons2/2699/PNG/512/scotiabank_logo_icon_170755.png" alt="ScotiaBank"
                        class="img-bank"> ScotiaBank </p>
                <hr>
                <p>Ana Karen Villanueva Hurtado</p>
                <p>Tarjeta: 4152 3134 3646 5153</p>
                <p>Banco: <img class="img-bank"
                        src="https://www.bbva.com/wp-content/uploads/2019/07/bbva-logo-nuevo-cuadrado-1024x1024.png"
                        alt="Banamex"> BBVA</p>
                <button @click="closeModal" class="btn btn-close-modal">Cerrar</button>
            </div>
        </div>
    </section>
</template>
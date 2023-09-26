<script setup>
import { ref } from 'vue';
const showModal = ref(true);
const content = 'Bienvenidos a la invitación de Karen & Jair';

const closeModal = () => {
    showModal.value = false;
    playSong();
};

const playSong = () => {
    var audio = document.getElementById('background-music');
    audio.play();
};

document.addEventListener("DOMContentLoaded", function () {
    var mensajeBienvenida = document.querySelector(".welcome-message");
    mensajeBienvenida.style.top = "0";
});

</script>

<template>
    <audio id="background-music">
        <source src="/audio/Legendarios.mp3" type="audio/mpeg">
        Tu navegador no soporta la reproducción de audio.
    </audio>
    <button style="display: none;" @click="playSong">Play</button>
    <div class="welcome-message text-center" v-if="showModal">
        <div class="modal-content">
            <p>{{ content }}</p>
            <button @click="closeModal" class="btn btn-close-modal">Ingresar</button>
        </div>
    </div>
</template>

<style scoped>
/* Estilos para el modal (inicialmente oculto) */
.welcome-message {
    position: fixed;
    top: -100%;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    display: flex;
    align-items: center;
    justify-content: center;
    transition: top 0.5s ease-in-out;
    border-radius: 10px;
}

.welcome-message.mostrar {
    top: 0;
    /* Muestra el mensaje desde arriba */
}

/* Estilos para el contenido del modal */
.modal-content {
    background-color: #fff;
    padding: 50px;
    width: 80%;
    max-width: 600px;
    margin: 20px auto;
    position: relative;
}

.btn-close-modal {
    background-color: #A347FF;
    color: white;
    width: 30%;
    margin: 0 auto;
    margin-top: 15px;
}

.modal-content>p {
    font-size: 25px;
}

@media (max-width: 768px) {
    .modal-content>p {
        font-size: 18px;
    }

    .btn-close-modal {
        background-color: #A347FF;
        color: white;
        width: 100%;
        margin: 0 auto;
        margin-top: 15px;
    }

}
</style>
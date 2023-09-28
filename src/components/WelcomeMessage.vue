<script setup>
import { ref } from 'vue';
const showModal = ref(true);
const content = 'Bienvenidos a la invitación de Karen & Jair';

const closeModal = () => {
    showModal.value = false;
    document.body.style.overflow = 'auto';
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
        <source src="/audio/Galactica.mp3" type="audio/mpeg">
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
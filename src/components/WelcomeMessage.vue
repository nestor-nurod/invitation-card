<script setup>
import { ref } from 'vue';
const showModal = ref(true);
const isStoped = ref(true);
const content = 'Bienvenidos a la invitación de Karen & Jair';

const closeModal = () => {
    showModal.value = false;
    document.body.style.overflow = 'auto';
    playSong();
};

const playSong = () => {
    var audio = document.getElementById('background-music');
    isStoped.value = false
    console.log(isStoped)
    audio.play();
};

const controlSong = () => {
    var audio = document.getElementById('background-music');
    if (isStoped.value) {
        console.log('Cancion reanuda')
        console.log(isStoped)
        isStoped.value = false
        audio.play()
    } else {
        console.log('Cancion para')
        console.log(isStoped)
        isStoped.value = true
        audio.pause()
    }
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
    <button class="btn-music" @click="controlSong"><span style="color: aliceblue;" :class="isStoped ? 'fa fa-circle-play':'fa fa-pause-circle'"></span></button>

    <div class="welcome-message text-center" v-if="showModal">
        <div class="modal-content">
            <p>{{ content }}</p>
            <button @click="closeModal" class="btn btn-close-modal">Ingresar</button>
        </div>
    </div>
</template>
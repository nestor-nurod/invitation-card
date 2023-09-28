<script setup>
import { ref, onMounted } from 'vue';

const days = ref(0);
const hours = ref(0);
const minutes = ref(0);
const seconds = ref(0);

// Fecha de finalización del temporizador (ajusta esta fecha según tus necesidades)
const endTime = new Date('2024-02-03T00:00:00');

function updateTimer() {
    const currentTime = new Date();
    const timeDifference = endTime - currentTime;

    days.value = Math.floor(timeDifference / (1000 * 60 * 60 * 24));
    hours.value = Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    minutes.value = Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60));
    seconds.value = Math.floor((timeDifference % (1000 * 60)) / 1000);

    if (timeDifference <= 0) {
        clearInterval(timerInterval);
    }
}

onMounted(() => {
    updateTimer();
    const timerInterval = setInterval(updateTimer, 1000);
});
</script>

<template>
    <section id="presentation" class="background-image">
        <div class="container">
            <div class="row text-center">
                <div class="col-12">
                    <h3>Karen & Jair</h3>
                </div>

                <div class="col-12">
                    <p class="large-text">Nuestra boda</p>
                </div>
                <div class="row timer">
                    <div class="col-3 col-sm-3">
                        <p>{{ days }}</p>
                    </div>
                    <div class="col-3 col-sm-3">
                        <p>{{hours}}</p>
                    </div>
                    <div class="col-3 col-sm-3">
                        <p>{{ minutes }}</p>
                    </div>
                    <div class="col-3 col-sm-3">
                        <p>{{ seconds }}</p>
                    </div>
                </div>
                <div style="margin-bottom: 300px;" class="row time">
                    <div class="col-3 col-sm-3">
                        <h4>Dias</h4>
                    </div>
                    <div class="col-3 col-sm-3">
                        <h4>Horas</h4>
                    </div>
                    <div class="col-3 col-sm-3">
                        <h4>Minutos</h4>
                    </div>
                    <div class="col-3 col-sm-3">
                        <h4>Segundos</h4>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>
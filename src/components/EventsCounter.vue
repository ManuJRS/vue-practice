<script setup>
import { ref } from 'vue';

// Crea una variable reactiva count con valor inicial 10.
// Haz que cada segundo disminuya en uno hasta llegar a 0, y cuando llegue, muestra el texto "¡Cuenta terminada!".
let number = ref(10)
let text = ref("Contando...")

const stopTimer = () => {
    if (number.value === 0) {
         clearInterval(timer)
         text.value = "Cuenta terminada"
    }
}

const timer = setInterval (() => {
    if (number.value > 0 ) {
         number.value --
    } else {
        stopTimer()
    }
}, 1000);

</script>

<template>
<h1>Esto es un contador</h1>
<p>{{ number }}</p>
<p>{{ text }}</p>
</template>

<style scoped>
button {
    margin-left: 10px;
}
</style>
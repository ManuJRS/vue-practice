<script setup>
import { ref } from 'vue';

// Crea un contador manual:
// Una variable count = ref(0)
// Un botón que diga “Sumar” y otro “Restar”.
// Al hacer clic en cada botón, aumenta o disminuye el contador respectivamente.

let count = ref(0)

const addOne = () => {
    count.value ++
}

const minusOne = () => {
    count.value --
}

</script>

<template>
<h1>Suma y Resta</h1>
<p>{{ count }}</p>
<button @click="addOne">Suma</button>
<button @click="minusOne">Resta</button>
</template>

<style scoped>
button { 
    margin: 10px;
}
</style>
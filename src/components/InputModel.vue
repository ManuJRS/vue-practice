<script setup>
import { ref } from 'vue';

// Crea un <input> y un <p>.
// Usa v-model para que al escribir en el input, el texto se muestre en el párrafo en tiempo real.
let text = ref("Este texto va a cambiar")

</script>

<template>
<h2>{{ text }}</h2>
<input type="text" v-model="text">
</template>
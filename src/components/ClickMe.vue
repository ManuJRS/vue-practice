<script setup>
import { ref } from 'vue';

// Crea un texto "Haz clic en mí" y cada vez que el usuario dé clic, cambia el color del texto entre rojo y azul.
// Pista:
// Puedes usar una variable booleana reactiva isRed = ref(true)
// y aplicar una clase condicional con :class="{ 'text-red-500': isRed, 'text-blue-500': !isRed }"

let isRed = ref(true)

</script>


<template>
<div class="box">
<p @click="isRed = !isRed" v-bind:class="{ 'text-red': isRed, 'text-blue': !isRed }">Haz click en el texto</p>
</div>
</template>

<style scoped>
.box {
    border: 1px, solid #fff;
    padding: 10px;
    border-radius: 20px;
    cursor: pointer;
    transition: all 0.5s ease-in-out ;
}

.box:hover {
    border: 1px, solid #fff;
    padding: 15px;
    transition: all 0.5s ease-in-out ;
}

.text-red {
    color: red;
}

.text-blue {
    color: blue;
}
</style>
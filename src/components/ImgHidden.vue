<script setup>
import { ref } from 'vue';

// Declara una variable reactiva imgSrc con la URL de una imagen (puede ser cualquier imagen online).
// Usa v-bind:src (o :src) para mostrar esa imagen en un <img>. https://upload.wikimedia.org/wikipedia/commons/8/85/2.5-year-old_fawn_male_pug.jpg


let seeDog = ref(true)


</script>

<template>
<div class="box">
<img v-bind:src="(seeDog ? '' : 'https://upload.wikimedia.org/wikipedia/commons/8/85/2.5-year-old_fawn_male_pug.jpg')" alt="">
<button @click="seeDog = !seeDog">Click 🐶</button>
</div>
</template>

<style scoped>
img {
    height: 400px;
    width: 400px;
    border-radius: 100%;
    object-fit: cover;
}
button {
    margin: 20px;
}
.box {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
</style>
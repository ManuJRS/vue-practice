<script setup>
import { ref } from 'vue';
// Declara una variable isBig = ref(false) y un botón que cambie su valor al hacer clic.
// Usa v-bind:class para que un <div> cambie entre las clases Tailwind w-20 h-20 bg-green-400 y w-40 h-40 bg-green-600.
let isBig = ref(false)

</script>

<template>
<div class="container">
<div v-bind:class="{'bigBox': isBig, 'smallBox': !isBig}">
</div>
<button @click="isBig = !isBig">Cambiar color</button>
</div>
</template>
<style scoped>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 250px;
    justify-content: center;
    
}
.smallBox {
  width: 100px;
  height: 100px;
  background-color: green;
  border-radius: 50%;
  transition: all 0.2s ease-in;
}

.bigBox {
  width: 200px;
  height: 200px;
  background-color: red;
  transition: all 0.2s ease-in;
}

button {
    position: absolute;
    margin-top: 290px;
}

</style>
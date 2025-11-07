<script setup>
import { ref } from 'vue';

// Queremos crear una app donde el usuario pueda:
// Escribir una tarea en un input.
// Agregarla a una lista.
// Marcarla como completada.
// Eliminarla si lo desea.

let newTask = ref("");
let tasks = ref([])
let addTask = () => {
    tasks.value.push(newTask.value)
    newTask.value = ""
}

</script>

<template>
    <h1>Lista de tareas</h1>
<div class="container">
<input type="text" v-model="newTask" placeholder="Agrega una tarea">
<div>
<button @click="addTask">Agregar Tarea</button>
</div>
<p v-for="(task, index) in tasks" :key="index">{{ index + 1 }}.- {{ task }}</p>
</div>
</template>

<style scoped>
.container {
display: flex;
flex-direction: column;
}

button {
    margin: 20px;
}
</style>
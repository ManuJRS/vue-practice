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
    if (!newTask.value.trim()) return // esto tuve que buscar como hacerlo con CGPT no encontraba la forma de eliminar espacios para que no registre solo espacios vacios

    //Tuve que buscar como armar un objeto dentro del push (no sabía que era posible)
    tasks.value.push({
        id: Date.now(),
        text:newTask.value.trim(),
        done: false
    })
    newTask.value = ""
}
let removeTask = (i) =>{
    tasks.value.splice(i, 1)
}

</script>

<template>
<div>
<h1>Lista de tareas</h1>
<p>Agrega tus tareas, puedes darle al check para marcar tareas realizadas y eliminar las que no quieras</p>
</div>
<div class="container">
<input class="input_task" type="text" v-model="newTask" placeholder="Agrega una tarea">
<button @click="addTask">Agregar Tarea</button>

<!--Tuve que buscar como hacer la logica del btn para elminar la tarea-->
<p v-bind:class="[task.done ? 'done p_task' : 'p_task']" v-for="(task, index) in tasks" :key="task.id">{{ index + 1 }}.- {{ task.text }} 
<button @click="removeTask(index)">Eliminar</button>
<input type="checkbox" class="check" v-model="task.done">
</p>

</div>
</template>

<style scoped>
.container {
display: flex;
flex-direction: column;
align-items: center;
}
button {
    margin: 20px;
}
.input_task {
width: 500px;
}
.p_task {
width: 120px;
}
.done { 
    text-decoration: line-through;
    opacity: .7;
    color: red;
}
</style>
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
<div class="container_tasks">
<p v-bind:class="[task.done ? 'done p_task' : 'p_task']" v-for="(task, index) in tasks" :key="task.id">
<span class="task_text">{{ index + 1 }}.- {{ task.text }}</span>
<span class="task_acction">
<button @click="removeTask(index)">Eliminar</button>
<input type="checkbox" class="check" v-model="task.done">
</span>
</p>
</div>
</div>
</template>

<style scoped>
.container {
display: flex;
flex-direction: column;
align-items: center;
width: auto;
}
button {
    margin: 20px;
}
.p_task {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 3px 0;
  border-bottom: 1px solid #eee;
}
.container_tasks {
    width: 500px;
}
.done { 
    text-decoration: line-through;
    opacity: .7;
    color: red;
}
.task_text {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-left: auto;
}
.task_text {
    flex: 1;
    text-align: left;
}
.input_task, .container_tasks  {
    width: 720px;
    max-width: 90%;
}
</style>
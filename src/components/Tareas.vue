<template>
    <div>
        <div v-bind:key="tarea.id" v-for="tarea in tareasList">
            <div>{{tarea.title}}</div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Tareas',
        props: ['tareasList']
    }
</script>

<style></style>
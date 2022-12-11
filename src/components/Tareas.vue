<template>
    <div>
        <div v-bind:key="tarea.id" v-for="tarea in tareasList">
            <TareaItem v-bind:tarea="tarea" v-on:delete-tarea="$emit('delete-tarea', tarea.id)" />
        </div>
    </div>
</template>

<script>
    import TareaItem from './TareaItem';

    export default {
        name: 'Tareas',
        props: ['tareasList'],
        components: {TareaItem}
    }
</script>

<style></style>
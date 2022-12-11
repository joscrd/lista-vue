<template>
  <div id="header"></div>

  <div id="main-container">
    <h2>Tareas</h2>
    <Tareas v-bind:tareasList="copyTareas" v-on:delete-tarea="deleteTarea"/>
  </div>
</template>

<script>
//import Search from './components/Search';
import Tareas from './components/Tareas';
//import TareaAdd from './components/TareaAdd'

export default {
  name: 'App',
  components: {
    Tareas
  },

  methods:{
    deleteTarea(id){
      this.tareas = this.tareas.filter(tarea => tarea.id != id);
      this.copyTareas = [...this.tareas];
    }
  },

  data() {
    return {
      tareas: [
        {
          id: 0,
          title: 'terminar presentacion vue.js',
          completed: false
        },
        {
          id: 1,
          title: 'hacer declaracion',
          completed: false
        },
        {
          id: 2,
          title: 'fumar mota',
          completed: true
        }
      ],
      copyTareas: []
    }
  },

  created(){
    this.copyTareas = [...this.tareas];
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
  }
  body{
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.5em;
    padding: 0;
    margin: 0;
  }
  #main-container{
    border: solid 1px #ccc;
    width: 600px;
    margin: 100px auto;
  }
  #header{
    background: black;
    padding: 10px;
  }
  h2{
    padding: 0 10px;
  }
</style>

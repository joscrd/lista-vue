<template>
    <div id="add-container">
        <form @submit="addTarea" >
            <input type="text" v-model="title">
        </form>
    </div>
</template>

<script>
    import { uuid } from 'vue-uuid';

    export default {
        name:'TareaAdd',
        data(){
            return {
                title:''
            }
        },
        methods:{
            addTarea(e){
                e.preventDefault();

                const newTarea = {
                    id: uuid.v4(),
                    title: this.title,
                    completed: false
                };

                this.title = '';
                this.$emit('add-tarea', newTarea);
            }
        }
    }
</script>

<style scoped>
    #add-container{
            padding: 10px;
        }
        input{
            padding: 10px;
            outline: none;
            border: solid 1px #ccc;
            width: 100%;
        }
</style>
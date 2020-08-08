<template>
    
        <div class="row">
            <p class="mx-auto" v-if="todos.length===0">Please wait.... fetching data...</p>
            <div class="col-md-3 mb-3" v-bind:key="todo.id" v-for="todo in todos">
                <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo',todo.id)" />
            </div>
        </div>
    
</template>

<script>
import TodoItem from './TodoItem'
export default {
    name:"Todos",
    components:{
        TodoItem
    },
    props: ["todos"]
}
</script>

<style scoped>
   
</style>
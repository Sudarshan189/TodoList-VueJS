<template>
    <div class="card" style="width: 18rem;">
        <div class="card-body">
            <h5 class="card-subtitle mb-2" v-bind:class="{'is-completed':todo.completed}">{{todo.title}}</h5>
            <div class="row">
                <div class="col-md-6">
                    <button v-if="todo.completed" v-on:click="markComplete" class="btn btn-success btn-sm">Complete</button>
                    <button v-else v-on:click="markComplete" class="btn btn-warning btn-sm">Incomplete</button>
                </div>
                <div class="col-md-6">
                    <button @click="$emit('del-todo',todo.id)" class="btn btn-danger btn-sm">Delete</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
   name:"TodoItem",
   props:["todo"],
   methods: {
       markComplete() {
           this.todo.completed=!this.todo.completed;
       }
   }
}
</script>

<style scoped>
   
    .is-completed {
        text-decoration: line-through;
    }
 
</style>
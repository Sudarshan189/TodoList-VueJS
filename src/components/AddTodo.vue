<template>
    <div class="add-todo">
        <form v-on:submit="addTodo">
            <div class="input-group mb-3">
                <input type="text" class="form-control" v-model="title" placeholder="Add Todos.." aria-label="Add Todos.." aria-describedby="basic-addon2">
                <div class="input-group-append">
                    <button class="btn btn-outline-success" type="submit">Add Todo</button>
                </div>
            </div>
        </form>
    </div>
</template>

<script>

export default {
    name:"AddTodo",
    data() {
        return{
            title:''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            let t=this.title.trim();
            if(t.length==0) {
                return;
            }
            const newTodo ={
                title:this.title,
                completed:false
            }
            //Send to perent
            this.$emit('add-todo', newTodo);
            this.title='';
        }
    }
}
</script>

<style scoped>
.add-todo {
    margin-top: 10px;
    padding-left: 25%;
    padding-right: 25%;
}

</style>
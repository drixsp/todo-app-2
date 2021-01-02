<template>
    <div class="add-todo">
        <!-- <form class="add-todo-form form-inline" @submit="addTodo">
            <input type="text" class="form-control add-todo-form">
            <input type="text" class="btn btn-primary" value="Submit">
        </form> -->
        <form class="form-inline add-todo">
            <div class="form-group mx-sm-3 mb-2">
                <input type="text" class="form-control" id="inputPassword2" placeholder="Add Todo">
            </div>
            <button type="submit" class="btn btn-primary mb-2">Add</button>
        </form>
    </div>
</template>

<script>
// import uuid from 'uuid'

export default {
    name: "AddTodo",
    data(){
        return{
            title:''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                title: this.title,
                completed: false
            }
            
            this.$emit('add-todo', newTodo);

            this.title = '';
        }
    }
}
</script>

<style scoped>
    .add-todo{
        margin-top: 10px;
        /* background-color: pink; */
        display: flex;
        justify-content: center;
        align-content: center;
    }
</style>
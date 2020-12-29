<template>
    <div class="add-todo">
        <form class="add-todo-form form-group" @submit="addTodo">
            <p class="add-text">Input here</p>
            <p class="add-btn"> Button here</p>
            <!-- <input class="add-todo-item form-control" type="text" name="title" v-model="title" placeholder="Add Todo..."> -->
            <!-- <input type="submit" value="Submit" class="add-todo-btn btn btn-primary"> -->
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
    .add-todo-form{
        display: flex;
        align-items: center;
    }

    .add-btn{
        align-self: center;
        flex: 1;
        background-color: green;
    }
    .add-text{
        align-self: center;
        flex: 5;
        background: pink;
    }

    .add-todo{
        /* display: flex; */
        /* align-items: center; */
        justify-content: flex-start;
        background: #f4f4f4;
        border-bottom: 1px #ccc solid;
    }
    form{
        margin-left: 50px;
        background-color: transparent;
        /* display: flex; */
    }
    .form-control{
        border: transparent;
        background-color: #f4f4f4;
    }

    /* input[type="text"]{
        flex: 10;
        padding: 5px;
    } */

    /* input[type="submit"]{
        flex: 2;
    } */
</style>
<template>
    <header class="header">
        <h1><strong>Todo List</strong></h1>
        <br>
        <p>A sample todo list app using Vue.js framework.</p>
        <br>
        <!-- <div class="btn-group">
            <router-link class="btn btn-primary" to="/">Home</router-link>
            <router-link class="btn btn-primary" to="/about">About</router-link>    
        </div> -->
        
        <AddTodo v-on:add-todo="addTodo" />
    </header>    
</template>

<script>
import AddTodo from '../AddTodo'
import axios from 'axios'

export default {
    components: {
        AddTodo
    },
    methods: {
        addTodo(newTodo){
        const {title, completed } = newTodo;

        axios.post('https://jsonplaceholder.typicode.com/todos', {
            title,
            completed
        })
        .then(res => this.todos = [...this.todos, res.data])
        .catch(err => console.log(err));
    }
    }
}
</script>

<style scoped>
    *{
        box-sizing: border-box;
        padding: 0;
        margin: 0;
    }
    .header{
        color:  #2b3f5c;
        text-align: center;
        padding: 20px;
        min-height: 150px;
        /* margin-top: 50px; */
        border-radius: 10px 10px 0px 0px;
    }
    .header a{
        color: #fff;
        /* padding-right: 5px; */
    }
</style>
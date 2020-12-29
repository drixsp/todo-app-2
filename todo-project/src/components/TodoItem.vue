<template>
    <div class="todo-item">
        <!-- <div class="item-container"> -->
            <input type="checkbox" v-on:change="markComplete" class="todo-check">
            <div class="todo-name" v-bind:class="{'is-complete':todo.completed}">{{todo.title}}</div>
            <button @click="$emit('del-todo', todo.id)" class="delete btn btn-danger">
                Delete
            </button>
        <!-- </div> -->
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete(){
            this.todo.completed = !this.todo.completed;
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
    /* .item-container{
        display: flex;
    } */
    .todo-item{
        display: flex;
        align-items: center;
        justify-content: flex-start;
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc solid;
    }
    .todo-name{
        margin-bottom: 0;
        display: inline-block;
        flex: 5;
    }
    input[type="checkbox"]{
        width: 20px;
        height: 20px;
    }
    .todo-check{
        flex: 0.5;
    }
    .todo-delete{
        flex: 1;
    }
    .is-complete{
        text-decoration: line-through;
    }
    .del{
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>
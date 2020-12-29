<template>
    <header class="header">
        <h1>Todo List</h1>
        <p>A sample todo list app using Vue.js framework.</p>
        
        <div class="btn-group">
            <router-link id="header-link" class="btn btn-primary" to="/">Home</router-link>
            <router-link id="header-link" class="btn btn-primary" to="/about">About</router-link>    
        </div>
        
    </header>    
</template>


<style scoped>
    *{
        box-sizing: border-box;
        padding: 0;
        margin: 0;
    }
    .header{
        background: #002261;
        color: #fff;
        text-align: center;
        padding: 10px;
        height: 150px;
    }
    .header a{
        color: #fff;
        /* padding-right: 5px; */
    }
    #header-link{
        margin: auto;
    }
</style>
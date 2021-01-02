<template>
  <div id="app">
    <div class="container">
      <div class="here">
        <div class="content">
        <div id="nav">
          <Header />
        </div>
        <router-view/>
      </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/layout/Header'
export default {
  name: 'app',
  components: {
    Header
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
}

*{
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.container{
  display: flex;
  justify-content: center;
}

.content{
  /* width: 50%; */
}

.here{
  width: 50%;
  background-color: #e1ffd6;
  margin-top: 100px;
  padding: 50px 50px 100px 50px;
  min-height: 50%;
  border-radius: 10px 10px 0px 0px;
  border-radius: 20px;

}

</style>

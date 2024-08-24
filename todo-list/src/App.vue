<template>
    <div id="app">
      <TodoList />
    </div>
  </template>
  

<script>
  import TodoList from './components/TodoList.vue';
  
  export default {
    components: {
      TodoList,
    },
  }
</script>


<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  font-weight: 300;
  margin-bottom: 20px;
}

input[type="text"] {
  padding: 10px;
  font-size: 16px;
  width: 80%;
  margin-bottom: 20px;
  border: 2px solid #2c3e50;
  border-radius: 5px;
  outline: none;
}

input[type="text"]:focus {
  border-color: #42b983;
}

button {
  background-color: #ff6b6b;
  border: none;
  padding: 5px 10px;
  color: white;
  cursor: pointer;
  border-radius: 3px;
  font-size: 14px;
}

button:hover {
  background-color: #ff4a4a;
}
</style>
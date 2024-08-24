<template>
  <div class="container">
    <h1>My To-Do List</h1>
    <input
      v-model="newTodo"
      @keyup.enter="addTodo"
      placeholder="Add a new task"
    />
    <ul>
      <li v-for="(item, index) in todos" :key="item.id">
        <TodoItem :item="item" @delete="deleteTodo(index)" />
      </li>
    </ul>
  </div>
</template>
  

<script>
import TodoItem from "./TodoItem.vue";

export default {
  components: {
    TodoItem,
  },
  data() {
    return {
      newTodo: "",
      todos: [],
    };
  },
  async created() {
    const response = await fetch(
      "https://jsonplaceholder.typicode.com/todos?_limit=10"
    );
    this.todos = await response.json();
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim()) {
        this.todos.push({
          title: this.newTodo,
          completed: false,
          id: Date.now(),
        });
        this.newTodo = "";
      }
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>


<style scoped>
.container {
  width: 400px;
  margin: 0 auto;
  padding: 20px;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

ul {
  list-style-type: none;
  padding: 0;
  width: 100%;
}

li {
  width: 100%;
  background-color: #f9f9f9;
  margin-bottom: 10px;
  padding: 10px;
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  transition: background-color 0.3s;
}

li:hover {
  background-color: #e9e9e9;
}
input {
  width: 75%;
  height: 20px;
  border-radius: 10px;
  padding: 3%;
}
</style>
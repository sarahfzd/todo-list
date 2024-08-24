<template>
  <div class="todo-item">
    <input type="checkbox" v-model="item.completed" />
    <span :class="{ completed: item.completed }">{{ item.title }}</span>
    <button @click="$emit('delete')">Delete</button>
  </div>
</template>
  

<script>
export default {
  props: ["item"],
};
</script>


<style scoped>
.completed {
  text-decoration: line-through;
}

.todo-item {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.todo-item input[type="checkbox"] {
  margin-right: 10px;
  margin-left: 10px;
  transform: scale(1.5);
}

.todo-item span {
  width: 100%;
  text-align: left;
  font-size: 18px;
}

.todo-item span.completed {
  text-decoration: line-through;
  color: #999;
}
</style>
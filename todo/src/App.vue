<script setup>
import AddSection from "./component/AddSection.vue";
import ListSection from "./component/ListSection.vue";
import { reactive } from "vue";

const state = reactive({
  todoText: null,
  todoList: [
    {
      id: 1,
      name: "desmond hume",
      completed: false,
    },
    {
      id: 2,
      name: "juliet burke",
      completed: false,
    },
    {
      id: 3,
      name: "john locke",
      completed: false,
    },
  ],
});

const addTodo = (event) => {
  state.todoList.push({
    id: new Date().getTime(),
    name: event,
    completed: false,
  });
  state.todoText= null
};
</script>

<template>
  <div class="container">
    <h1>Todo List</h1>
    {{ state.todoList }} <br /><br />
    <!-- <AddSection /> -->
    <input
      type="text"
      placeholder="todo app.vue"
      v-model="state.todoText"
      @keydown.enter="addTodo(state.todoText)"
    />
    <ListSection :listTodo="state.todoList" @checkedState="!state.todoList.completed" />
  </div>
</template>

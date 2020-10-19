<template>
  <div id="app">
    <img alt="Notepad Icon" src="./assets/notepad.png" />
    <div class="container">
      <todo-card v-for="(todoItem, i) in todoItems" :key="i" :todoObject="todoItem"></todo-card>
    </div>
  </div>
</template>

<script>
// axios
import axios from 'axios';

// components
import TodoCard from "./components/todo-card.vue";

export default {
  name: "App",
  components: {
    TodoCard,
  },
  data: function () {
    return {
      someText: "hello my name is dan",
      todoItems: []
    };
  },
  methods: {},
  mounted: function () {
    const axiosInstance = axios.get('http://localhost:8000/todo-item');
    axiosInstance.then((response) => {
      this.todoItems = response.data;
    }).catch((error) => {
      console.log(error);
    });
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
  <div id="app">
    <img alt="Notepad Icon" src="./assets/notepad.png" />
    <div class="container">
      <todo-card v-for="(todoItem, i) in todoItems" :key="i" :todoObject="todoItem"></todo-card>
    </div>
  </div>
</template>

<script>
import TodoCard from "./components/todo-card.vue";

export default {
  name: "App",
  components: {
    TodoCard,
  },
  data: function () {
    return {
      someText: "hello my name is dan",
      todoItems: [
        {todo: 'Do the washing up'},
        {todo: 'take out the bins'},
        {todo: 'clean bathroom'},
        {todo: 'feed cats'},
      ] 
    };
  },
  methods: {},
  mounted: function () {
    setTimeout(() => {
      this.someText = "no my name is james";
    }, 5000);
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

<template>
  <div id="app">
    <h1>My To-Do-List</h1>
    <ToDoForm @todo-added="addToDo" />
    <ul>
      <li v-for="item in TodoItems" :key="item.id">
        <TodoItem :label="item.label" :done="item.done" :id="item.id" />
      </li>
    </ul>
  </div>
</template>


<script>
import TodoItem from "@/components/ToDoItem.vue";
import uniqueId from "lodash.uniqueid";
import ToDoForm from "@/components/ToDoForm.vue";

export default {
  name: "app",
  components: {
    TodoItem,
    ToDoForm,
  },
  data() {
    return {
      TodoItems: [
        { id: uniqueId("todo-"), label: "Learn Vue", done: false },
        {
          id: uniqueId("todo-"),
          label: "Create a Vue project with the CLI",
          done: false,
        },
        { id: uniqueId("todo-"), label: "Have fun", done: false },
        { id: uniqueId("todo-"), label: "Create a to-do list", done: false },
      ],
    };
  },
  methods: {
    addToDo(toDoLabel) {
      // console.log("to-do added", toDoLabel);
      this.TodoItems.push({
        id: uniqueId("todo-"),
        label: toDoLabel,
        done: false,
      });
    },
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
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

li {
  list-style-type: none;
}
</style>

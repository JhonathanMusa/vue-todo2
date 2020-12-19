<template>
  <div>
    <input type="checkbox" id="todo-item" v-bind:checked="isDone" />
    <!-- <input type="checkbox" id="todo-item" :checked="isDone" /> -->
    <!-- <label for="todo-item">{{ label }}</label> -->
    <label :for="id">{{ label }}</label>
  </div>
</template>

<script>
import uniqueid from "lodash.uniqueid";
export default {
  props: {
    label: { required: true, type: String },
    done: { default: false, type: Boolean },
    id: { required: true, type: String },
  },
  data() {
    return {
      isDone: this.done,
      /* id: uniqueid("todo-"), */
    };
  },
};
</script>
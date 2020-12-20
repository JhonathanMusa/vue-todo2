<template>
  <div class="form">
    <form @submit.prevent="onSubmit">
      <label for="new-todo-input"> What needs to be done? </label><br>
      <input
        type="text"
        id="new-todo-input"
        name="new-todo"
        autocomplete="off"
        v-model.lazy.trim="label"
      />
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "ToDoForm",
  methods: {
    onSubmit() {
      // console.log("Label value: ", this.label);
      if (this.label === "") {
        return;
      }
      this.$emit("todo-added", this.label);
      this.label = "";
    },
  },
  data() {
    return {
      label: "",
    };
  },
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
}

.form input{
  border-radius: 5px;
  border: 1px solid #aaa;
  padding: 10px;
}

.form button{
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #aaa;
  margin-top: 10px;
  
}
</style>

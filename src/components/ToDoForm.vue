<template>
  <div class="form">
    <form @submit.prevent="onSubmit">
      <h2 class="label-wrapper">
      <label for="new-todo-input" class="label__lg"> What needs to be done? </label>
      </h2>
      <input
        type="text"
        id="new-todo-input"
        name="new-todo"
        autocomplete="off"
        v-model.lazy.trim="label"
        class="input__lg"
      />
      <button type="submit" class="btn btn__primary btn__lg">Add</button>
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
/*.form {
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
  
} */
</style> 

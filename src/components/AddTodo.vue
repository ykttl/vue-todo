<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title">
      <input type="submit" value="submit">
    </form>
  </div>
</template>

<script>
// import uuid from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault(); // for form in html
      const newTodo = {
        // id: uuid.v4(),
        title: this.title,
        completed: false
      };
      //send up to parent
      this.$emit("add-todo", newTodo);
    }
  }
};
</script>

<style  scoped>
</style>

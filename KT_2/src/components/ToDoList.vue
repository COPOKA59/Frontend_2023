<template>
  <div>
    <h3>Cписок покупок</h3>
    <to-do-item
        v-for="(todo, i) in todos"
        :key="todo.id"
        :todo="todo"
        @remove="$emit('remove',todo)"
    />
  </div>
</template>

<script>
import ToDoItem from "@/components/ToDoItem.vue";

export default {
  components: {ToDoItem},
  props: {
    todos: {
      type:Array,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.todo {
  display: flex;
  justify-content: space-between;
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}
</style>
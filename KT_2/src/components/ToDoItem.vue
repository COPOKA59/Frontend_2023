<template>
  <div class="todo">
    <div v-bind:class="{done: todo.completed}">
      <input type="checkbox" v-on:change="(todo.completed = !todo.completed)">
      <strong>Задача № {{ todo.id }}: </strong>&nbsp;
      &nbsp;{{ todo.title }}
    </div>
    <my-button class="btn" type="submit"
            @click="$emit('remove',todo)"
    >
      Удалить {{todo.id}}
    </my-button>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";

export default {
  components: {MyButton},
  props:{
    todo:{
      type:Object,
      required:true,
    }
  }
}
</script>

<style lang="scss" scoped>
.done {
  text-decoration: line-through;
}
</style>
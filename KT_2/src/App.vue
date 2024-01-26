<template>
  <div>Проект КТ 2_2. ToDo приложение</div>
  <hr>
  <div class="app">
    <to-do-form
        @create="createToDo"
    >

    </to-do-form>

    <to-do-list
        :todos="todos"
        @remove="removeTodo"
    >

    </to-do-list>
  </div>
</template>

<script>
import ToDoList from "@/components/ToDoList.vue";
import ToDoForm from "@/components/ToDoForm.vue";
export default {
  components: {
    ToDoForm, ToDoList
  },
  data() {
    return {
      todos: [
        { id: 1, title: 'Купить молоко', completed: false },
        { id: 2, title: 'Купить хлеб', completed: false },
        { id: 3, title: 'Купить масло', completed: false }
      ],
    }
  },
  methods: {
    createToDo(todo) {
      this.todos.push(todo);
    },
    removeTodo(todo) {                
      this.todos = this.todos.filter(t => t.id !== todo.id) //пересоздаем массив
      console.log(todo.id);  //можно убрать, просто для контроля
    }
  }
}
</script>

<style>

.app {
  text-align: center;
  color: #2c3e50;
  margin-top: 40px;
}
</style>

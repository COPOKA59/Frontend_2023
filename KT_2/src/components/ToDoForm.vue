<template>
  <form @submit.prevent>
    <h4>Создать задачу</h4>
    <input
        class="input"
        type="text"
        v-model="todo.title"
        placeholder="Задача"
    >
    <my-button
        type="submit"
        @click="createToDo"
        style="align-self: flex-end; margin-top:15px "
    >Создать
    </my-button>
  </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
export default {
  components: {MyButton},
  data() {
    return {
      todo: {
        title: '',
      }
    }
  },
  methods: {
    createToDo(todo) {
      this.todo.id =Date.now();
      this.$emit('create', this.todo)
      this.todo={
        title: '',
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.input {
  width: 100%;
  border: 2px solid teal;
  padding: 10px 15px;
  margin-top: 10px;

}


form {
  display: flex;
  flex-direction: column;
}
</style>
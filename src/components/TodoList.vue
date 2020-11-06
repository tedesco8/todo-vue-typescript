<template>
  <div>
    <TodoForm @newTodo="newTodo($event)" />
    <hr />
    <button @click="removeTodos" class="btn btn-dark btn-block">
      Eliminar todos
    </button>
    <hr />
    <table class="table">
      <thead>
        <tr>
          <th>ID</th>
          <th>Todo</th>
          <th>Eliminar</th>
        </tr>
      </thead>
      <tbody v-if="todos.length > 0">
        <TodoItem
          v-for="(todo, index) in todos"
          :key="index"
          :todo="todo"
          :index="index"
          @removetodo="removeTodo($event)"
        />
      </tbody>
      <tbody v-else>
        <tr>
          <td colspan="3">No hay todos</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import TodoForm from "@/components/TodoForm.vue";
import TodoItem from "@/components/TodoItem.vue";
@Component({
  components: {
    TodoForm,
    TodoItem,
  },
})
export default class TodoList extends Vue {
  todos: Array<any> = [];

  newTodo(todo: string) {
    this.todos.push(todo);
  }
  removeTodo(index: number) {
    this.todos.splice(index, 1);
  }
  removeTodos() {
    this.todos = [];
  }
}
</script>

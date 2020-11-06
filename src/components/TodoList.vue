<template>
  <div>
    <TodoForm @newTodo="newTodo($event)" />
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
        <tr v-for="(todo, index) in todos" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ todo }}</td>
          <td>
            <button @click="removeTodo(index)" class="btn btn-danger btn-block">
              Eliminar todo
            </button>
          </td>
        </tr>
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
import TodoForm from '@/components/TodoForm.vue'
@Component({
    components: {
        TodoForm
    }
})
export default class TodoList extends Vue {
  todos: Array<any> = [];

  newTodo(todo: any) {
    this.todos.push(todo);
  }
  removeTodo(index: any) {
    this.todos.splice(index, 1);
  }
  removeTodos() {
    this.todos = [];
  }
};
</script>

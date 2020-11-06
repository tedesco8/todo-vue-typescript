<template>
  <form @submit.prevent="addTodo">
    <div class="form-group">
      <label for="todo">TODO</label>
      <input v-model="todo" type="text" autocomplete="off" class="form-control" id="todo" />
    </div>
    <button type="submit" class="btn btn-primary btn-block">
      Añadir todo
    </button>
  </form>
</template>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class TodoForm extends Vue {
    // eslint-disable-next-line
    todo: string = '';

    addTodo() {
        this.$emit('newTodo', this.todo);
        this.todo = '';
    }
}
</script>

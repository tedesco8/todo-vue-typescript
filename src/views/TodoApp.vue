<template>
  <div class="todo">
    <TodoList />
  </div>
</template>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
// [skip other imports]
import TodoList from '@/components/TodoList.vue';

@Component({
  components: {
    TodoList,
  },
})
export default class TodoApp extends Vue {}
</script>

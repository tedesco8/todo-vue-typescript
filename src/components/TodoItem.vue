<template>
    <tr>
      <td>{{ index + 1 }}</td>
      <td>{{ todo }}</td>
      <td>
        <button
          @click="$emit('removetodo', index)"
          class="btn btn-danger btn-block"
        >
          Eliminar todo
        </button>
      </td>
    </tr>
</template>
<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class TodoItem extends Vue {
  @Prop() todo!: string;
  @Prop() index!: number;
}
</script>

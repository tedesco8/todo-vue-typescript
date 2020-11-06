<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br />
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener"
        >vue-cli documentation</a
      >.
    </p>
    <h3>Installed CLI Plugins</h3>
    <p @click="click">{{ fullName }}</p>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
  // eslint-disable-next-line
  name: string = "Pablo";
  // eslint-disable-next-line
  surname: string = "Tedesco";

  get fullName() {
    return `${this.name} ${this.surname}`;
  }

  click() {
    alert("ALERT");
  }

  mounted() {
    console.log("Component mounted");
  }
  destroyed() {
    console.log("Component destroyed")
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

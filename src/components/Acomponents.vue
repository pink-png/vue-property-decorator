<template>
  <div class="hello">
    {{ msg }}
    <div class="btnaddreduce">
      <button @click="btnx('add')">+</button>
      <span>{{ coust }}</span>
      <button @click="btnx('reduce')">-</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class Acomponents extends Vue {
  @Prop() private msg!: string;

  private coust = 0;

  // eslint-disable-next-line @typescript-eslint/typedef
  private btnx(type: string) {
    type === "add" ? this.coust++ : this.coust--;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.btnaddreduce {
  width: 100px;
  height: 26px;
  border: 1px solid #cccccc;
  display: flex;
  justify-content: space-between;
  text-align: center;
  line-height: 26px;
}
button {
  width: 26px;
  height: 26px;
}
</style>

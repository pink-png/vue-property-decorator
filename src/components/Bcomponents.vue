<template>
  <div class="hello">
    {{ msg }}
    <div class="btnaddreduce">
      <button @click="addToCount">+</button>
      <span>{{ coust }}</span>
      <button @click="resetCount">-</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue, Emit } from "vue-property-decorator";

@Component
export default class Bcomponents extends Vue {
  @Prop() private msg!: string;

  private coust = 0;

  @Emit("addTo")
  addToCount() {
    return 1;
  }

  @Emit("resetTo")
  resetCount() {
    return -1;
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

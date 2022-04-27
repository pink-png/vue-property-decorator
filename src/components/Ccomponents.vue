<template>
  <div class="hello">
    {{ syncedName }}
    <div class="btnaddreduce">
      <button @click="btnsync">点击同时修改子和父的数据</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue, PropSync } from "vue-property-decorator";

@Component
export default class Ccomponents extends Vue {
  @Prop() private msg!: string;
  @PropSync("name", { type: String }) syncedName!: string;

  btnsync(): void {
    this.syncedName = "点击修改的数据";
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.btnaddreduce {
  width: 200px;
  height: 26px;
  display: flex;
  justify-content: space-between;
  text-align: center;
  line-height: 26px;
}
</style>

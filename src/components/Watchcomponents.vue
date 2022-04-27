<template>
  <div class="hello">
    {{ tempname }}
    <div class="btnaddreduce">
      <button @click="btn">点击同时修改想要监视的数据</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Watch } from "vue-property-decorator";

@Component
export default class Watchcomponents extends Vue {
  private tempname = "想要监视的数据";
  @Watch("tempname", { immediate: true, deep: true })
  watchchufa(val: string, oldVal: string) {
    console.log("触发watch--新的数据", val);
    console.log("触发watch--老的数据", oldVal);
  }
  btn() {
    this.tempname = "点击修改的数据";
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

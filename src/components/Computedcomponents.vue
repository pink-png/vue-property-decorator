<template>
  <div class="hello">
    {{ count }}
    {{ getCount }}
    <div class="btnaddreduce">
      <button @click="btn">点击修改的数据</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class Computedcomponents extends Vue {
  private count = 111;

  btn() {
    this.count = 222;
  }

  get getCount(): number {
    return this.count + 1;
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

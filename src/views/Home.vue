<template>
  <div class="home">
    <HelloWorld :msg="title" @addToCount="add" @resetCount="reset" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "@/components/HelloWorld.vue";

@Component({
  name: "Home",
  components: {
    HelloWorld,
  },
})
export default class extends Vue {
  private title = "Welcome to Your Vue.js App";

  add = () => {
    alert();
  };
  reset = () => {
    alert();
  };

  created() {
    console.log("created");
  }
  mounted() {
    console.log("mounted");
  }
  destroyed() {
    console.log("destroyed");
  }
}
</script>


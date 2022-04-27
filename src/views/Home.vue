<template>
  <div class="home">
    <!-- <Acomponents :msg="title" /> -->
    <!-- <Bcomponents :msg="title" @addTo="add" @resetTo="reset" /> -->
    <!-- <Ccomponents :name.sync="title" /> -->
    <!-- <Watchcomponents /> -->
    <Computedcomponents />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Acomponents from "@/components/Acomponents.vue";
import Bcomponents from "@/components/Bcomponents.vue";
import Ccomponents from "@/components/Ccomponents.vue";
import Watchcomponents from "@/components/Watchcomponents.vue";
import Computedcomponents from "@/components/Computedcomponents.vue";
@Component({
  name: "Home",
  components: {
    Acomponents,
    Bcomponents,
    Ccomponents,
    Watchcomponents,
    Computedcomponents,
  },
})
export default class extends Vue {
  private title = "刚开始的title";
  private count = 0;

  // eslint-disable-next-line @typescript-eslint/typedef
  add(e: number) {
    this.title += e;
  }
  // eslint-disable-next-line @typescript-eslint/typedef
  reset(e: number) {
    this.title += e;
  }

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


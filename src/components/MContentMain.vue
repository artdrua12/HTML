
<template>
  <div class="mContentMain">
    <header-content-main class="top"></header-content-main>
    <default-comp class="left" title="LIVE CHART"></default-comp>
    <default-comp class="right" title="SPECTRA"></default-comp>
  </div>
</template>

<script>
import HeaderContentMain from "./HeaderContentMain.vue";
import DefaultComp from "./DefaultComp.vue";
export default {
  props: {
    title: {
      default: "default value"
    },
    height: {
      default: 100
    }
  },
  data() {
    return {};
  },
  components: {
    HeaderContentMain,
    DefaultComp
  }
};
</script>

<style scoped>
.mContentMain {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  grid-template-rows: repeat(2, 1fr);
  grid-gap: 15px;
}
.top {
  grid-column: 1 / 3;
  grid-row: 1/2;
}
.left {
  grid-column: 1 / 2;
  grid-row: 2/3;
}
.right {
  grid-column: 2 / 3;
  grid-row: 2/3;
}
</style>



<template>
  <div class="mContentMain">
    <header-content-main class="header"></header-content-main>
    <default-comp class="left" title="LIVE CHART">
      <img src="../assets/chart.png" alt="chart">
    </default-comp>
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
  grid-template-rows: 1fr 47%;
  grid-gap: 15px;
}
.header{
  grid-column: 1 / 3;
  grid-row: 1/2;
}
.left {
  grid-column: 1 / 2;
  grid-row: 2/3;
  overflow: hidden;
}
.right {
  grid-column: 2 / 3;
  grid-row: 2/3;
  overflow: hidden;
}
</style>


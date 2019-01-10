
<template>
  <div class="mContentMain" :style="{'height': height + 'px'}">
    <header>h</header>
    <default-comp class="left" :title='fff' :height="230"></default-comp>
    <default-comp class="right" :title="item" :height="230"></default-comp>
  </div>
</template>

<script>
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
    DefaultComp
  }
};
</script>

<style scoped>
.mContentMain {
  display: grid;
  grid-template-columns: 60% 40%;
  grid-template-rows: repeat(2, 50%);
  border: 1px solid blue;
}
header {
  grid-column: 1 / 3;
  grid-row: 1/2;
  height: 250px;
}
.left {
  grid-column: 1 / 2;
  grid-row: 2/3;
}
.right{
  grid-column: 2 / 3;
  grid-row: 2/3;
}
</style>


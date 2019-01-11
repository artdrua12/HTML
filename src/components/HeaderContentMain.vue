<template>
  <div class="headerContentMain">
    <nav>n</nav>
    <section>s</section>
    <aside class="left">l</aside>
    <aside class="right">r</aside>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>

<style scoped>
.headerContentMain {
  display: grid;
  grid-template-columns: 150px repeat(2, 1fr);
  grid-template-rows: 35px 1fr;
}
.left {
  grid-column: 2 / 3;
  grid-row: 2/3;
  background-color: azure;
}
.right {
  grid-column: 3 / 4;
  grid-row: 2/3;
  background-color: rgb(113, 160, 160);
}
nav {
  grid-column: 1 / 4;
  grid-row: 1/2;
  background-color: rgb(228, 204, 188);
}
section {
  grid-column: 1 / 2;
  grid-row: 2/3;
  background-color: rgb(214, 224, 185);
}
</style>

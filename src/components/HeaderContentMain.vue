<template>
  <div class="headerContentMain">
    <nav>
      <md-tabs>
        <md-tab v-for="(item,key) in navArray" :key="key" :md-label="item"></md-tab>
      </md-tabs>
    </nav>

    <section>s</section>
    <aside class="left">l</aside>
    <aside class="right">r</aside>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navArray: [
        "WORKLIST",
        "RUN",
        "TO DO: 23 injections",
        "02:15:0",
        "METHODS:Metod 1.amx (00:00/04:30)",
        "SINGLE RUN"
      ]
    };
  }
};
</script>

<style scoped>
.headerContentMain {
  display: grid;
  grid-template-columns: 150px repeat(2, 1fr);
  grid-template-rows: auto 1fr;
  border: 1px solid gray;
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
}
section {
  grid-column: 1 / 2;
  grid-row: 2/3;
  background-color: rgb(214, 224, 185);
}
</style>

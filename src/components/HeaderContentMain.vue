<template>
  <div class="headerContentMain">
    <nav>
      <md-tabs>
        <md-tab v-for="(item,key) in gorisontalNav" :key="key" :md-label="item"></md-tab>
      </md-tabs>
    </nav>

    <md-list class="section">
      <template v-for="(item,key) in vertiralNav">
        <md-list-item :key="key">{{item}}</md-list-item>
        <md-divider :key="key"></md-divider>
      </template>
    </md-list>

    <aside class="left">l</aside>
    <aside class="right">r</aside>
    <footer></footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      gorisontalNav: [
        "WORKLIST",
        "RUN",
        "TO DO: 23 injections",
        "02:15:0",
        "METHODS:Metod 1.amx (00:00/04:30)",
        "SINGLE RUN"
      ],
      vertiralNav: ["ALS", "Inlets", "Columns"]
    };
  }
};
</script>

<style scoped>
.headerContentMain {
  display: grid;
  grid-template-columns: 150px repeat(2, 1fr);
  grid-template-rows: auto 1fr auto;
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
.section {
  grid-column: 1 / 2;
  grid-row: 2/3;
  background-color: rgb(239, 241, 245);
}
footer {
  grid-column: 1 / 4;
  grid-row: 3/4;
  height: 40px;
  background-color: rgb(255, 255, 254);
  border-top: 1px solid gray;
}
</style>

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
        <md-divider :key="key+100"></md-divider>
      </template>
    </md-list>

    <aside class="left">l</aside>
    <aside class="right">r</aside>
    <footer>
      <div class="butLeft">
        <i class="material-icons">add_circle_outline</i>
        <span>ddd</span>
      </div>
      <div class="butLeft">
        <i class="material-icons">adjust</i>
        <span>ddd</span>
      </div>
      <md-button class="clear md-primary butRight">Cansel</md-button>
      <md-button class="md-raised md-primary butRight">Save as</md-button>
      <md-button class="md-raised md-primary butRight">Save</md-button>
    </footer>
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
  overflow: hidden;
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
.clear {
  border: 1px solid blue;
}
.butRight {
  float: right;
    border-radius: 20px;
  width: 85px;
  height: 30px;
}
.section {
  grid-column: 1 / 2;
  grid-row: 2/3;
  background-color: rgb(239, 241, 245);
}
div.butLeft {
  display: inline;
  color: gray;
  border: 1px solid red;
  height: 100%;
}
nav {
  grid-column: 1 / 4;
  grid-row: 1/2;
}
footer {
  grid-column: 1 / 4;
  grid-row: 3/4;
  height: 44px;
  background-color: rgb(255, 255, 254);
  border-top: 1px solid gray;
}

</style>

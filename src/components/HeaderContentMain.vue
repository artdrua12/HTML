<template>
  <div class="headerContentMain">
    <nav>
      <md-tabs>
        <md-tab v-for="(item,key) in gorisontalNav" :key="key" :md-label="item"></md-tab>
      </md-tabs>
    </nav>

    <md-list class="section">
      <template v-for="(item,key) in vertiralNav">
        <md-list-item :class="{cheked: item=='Columns' }" :key="key">{{item}}</md-list-item>
        <md-divider :key="key+100"></md-divider>
      </template>
    </md-list>

    <h-cont-main-left class="left"></h-cont-main-left>
    <h-cont-main-right class="right"></h-cont-main-right>
    <footer>
      <div class="butLeft" v-for="(item, key) in footer" :key="key">
        <i class="material-icons">{{item.icon}}</i>
        <span>{{item.span}}</span>
      </div>
      <md-button class="clear md-primary butRight">Cansel</md-button>
      <md-button class="md-raised md-primary butRight">Save as</md-button>
      <md-button class="md-raised md-primary butRight">Save</md-button>
    </footer>
  </div>
</template>

<script>
import HContMainRight from "./HContMainRight.vue";
import HContMainLeft from "./HContMainLeft.vue";
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
      vertiralNav: ["ALS", "Inlets", "Columns"],
      footer: [
        { icon: "add_circle_outline", span: "New" },
        { icon: "adjust", span: "Open" }
      ]
    };
  },
  components: {
    HContMainRight,
    HContMainLeft
  }
};
</script>

<style scoped>
.headerContentMain {
  display: grid;
  grid-template-columns: 140px repeat(2, 1fr);
  grid-template-rows: auto 1fr 50px;
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
  overflow: hidden;
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
.cheked {
  background-color:  rgb(255, 255, 254);
}
div.butLeft {
  display: inline-flex;
  flex-direction: column;
  color: gray;
  align-items: center;
  margin-left: 20px;
  margin-top: 3px;
}
nav {
  grid-column: 1 / 4;
  grid-row: 1/2;
  border-bottom: 1px solid gray;
}
span {
  font-size: 0.8rem;
}
footer {
  grid-column: 1 / 4;
  grid-row: 3/4;
  padding: 3px 0px;
  background-color: rgb(255, 255, 254);
  border-top: 1px solid gray;
}
</style>

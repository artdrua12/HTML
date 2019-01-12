
<template>
  <div class="mycontent">
    <header class="left">
      <md-menu>
        <md-button md-menu-trigger>
          <md-icon>reorder</md-icon>
        </md-button>
      </md-menu>

      <md-menu>
        <md-button md-menu-trigger>instruments
          <md-icon>keyboard_arrow_down</md-icon>
        </md-button>
        <md-menu-content>
          <md-menu-item>My Item 1</md-menu-item>
          <md-menu-item>My Item 2</md-menu-item>
          <md-menu-item>My Item 3</md-menu-item>
        </md-menu-content>
      </md-menu>

      <md-menu v-for="(item,key) in text" :key="key">
        <md-button md-menu-trigger>{{item}}</md-button>
      </md-menu>
    </header>

    <header class="right">
      <md-menu class="border">
        <md-button md-menu-trigger>
          <md-icon>account_circle</md-icon>Alexander
        </md-button>
      </md-menu>

      <md-menu class="border">
        <md-button md-menu-trigger>Eng
          <md-icon>keyboard_arrow_down</md-icon>
        </md-button>
        <md-menu-content>
          <md-menu-item>Eng</md-menu-item>
          <md-menu-item>Rus</md-menu-item>
          <md-menu-item>Other</md-menu-item>
        </md-menu-content>
      </md-menu>

      <md-menu class="border">
        <md-button md-menu-trigger>
          <md-icon class="color">lock_open</md-icon>
        </md-button>
      </md-menu>
    </header>

    <section>
      <md-button class="md-icon-button md-raised">
        <md-icon class="button">keyboard_arrow_left</md-icon>
      </md-button>
      <default-comp
        v-for="(item,key) in main"
        :key="key"
        :title="item.title"
        :color="item.color"
        :height="item.height"
      > <h1>slot</h1> </default-comp>
    </section>
    <m-content-main class="main"></m-content-main>
  </div>
</template>

<script>
import DefaultComp from "./DefaultComp.vue";
import MContentMain from "./MContentMain.vue";
export default {
  data() {
    return {
      text: ["Widgets", "View", "Administration"],
      main: [
        { title: "Sampler", color: "green", height: 20 },
        { title: "Quat. Pump", color: "orange", height: 20 }
      ]
    };
  },
  components: {
    DefaultComp,
    MContentMain
  }
};
</script>

<style scoped>
.mycontent {
  display: grid;
  grid-template-columns: 200px repeat(2, AUTO);
  grid-template-rows: 47px 1fr;
}
.main {
  grid-column: 2 / 4;
  grid-row: 2/3;
  background-color: rgb(239, 241, 245);
  overflow: hidden;
  padding: 15px;
}
.border {
  border-left: 1px solid gray;
}
.md-menu {
  display: flex;
  justify-content: center;
}
i.md-icon.color {
  color: rgb(11, 207, 207);
}
header.left {
  grid-column: 1 / 3;
  grid-row: 1/2;
  justify-content: flex-start;
}
header.right {
  grid-column: 3 / 4;
  grid-row: 1/2;
  justify-content: flex-end;
}
header {
  display: flex;
  background-color: rgb(255, 255, 255);
  align-items: center;
  overflow: hidden;
}
section {
  grid-column: 1 / 2;
  grid-row: 2/3;
  background-color: rgb(228, 233, 236);
  padding: 15px;
  display: flex;
  flex-direction: column;
  border-right: 1px solid gray;
  box-shadow: -3px 0px 7px -1px #8d8a8a inset;
}
</style>


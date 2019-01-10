
<template>
  <div class="mycontent">
    <header class="left">
      <i class="material-icons">reorder</i>

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

      <i class="material-icons color border">lock_open</i>
    </header>

    <section>section</section>
    <main>main</main>
  </div>
</template>

<script>
import DefaultComp from "./DefaultComp.vue";
export default {
  data() {
    return {
      text: ["Widgets", "View", "Administration"]
    };
  },
  components: {
    DefaultComp
  }
};
</script>

<style scoped>
.mycontent {
  display: grid;
  grid-template-columns: repeat(2, 1fr) 270px;
  grid-template-rows: 47px 1fr;
}
.border{
  border-left: 1px solid gray
}
.md-menu {
  display: flex;
  flex: 0 1 120px;
  justify-content: center;
}
i.color {
  color: rgb(11, 207, 207);
  padding:  0px 5px 0px 7px;
}
i.md-icon {
  margin: -3px 0px 0px -2px;
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
  background-color: rgb(226, 231, 235);
}
main {
  grid-column: 2 / 4;
  grid-row: 2/3;
  background-color: rgb(226, 231, 235);
}
i {
  margin: -2px 15px 0px 15px;
  font-size: 1.8rem;
}
</style>



<template>
  <div class="defaultComponent" :style="{'height': height + '%'}">
    <header>
      <div v-if="color" class="square" :style="{'background': color}"></div>
      <h1>{{title}}</h1>
    </header>
    <main>
      <slot></slot>
    </main>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      default: "default value"
    },
    height: {
      default: 100
    },
    color: {}
  },
  data() {
    return {};
  }
};
</script>

<style scoped>
.defaultComponent {
  width: 100%;
  height: 100%;
  display: flex;
  flex-wrap: wrap;
  background-color: rgb(255, 255, 254);
  border: 1px solid gray;
  margin-bottom: 20px;
}
.square {
  width: 15px;
  height: 15px;
  margin-right: 7px;
}
header,
main {
  flex: 1 1 51%;
  display: flex;
  align-items: center;
}
main {
  justify-content: space-around;
}
header {
  border-bottom: 1px solid gray;
  height: 30px;
  padding-left: 10px;
}
</style>


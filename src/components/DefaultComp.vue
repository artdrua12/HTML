
<template>
  <div class="defaultComponent" :style="{'height': height + 'px'}">
    <header>
      <h1>{{title}}</h1></header>
    <main>m</main>
  </div>
</template>

<script>
export default {
  props:{
    title:{
      default:"default value"
    },
    height:{
      default:100
    }
  },
  data() {
    return {
     
    };
  }
};
</script>

<style scoped>
.defaultComponent{
  width: 100%;
  height: 100%;
  display: flex;
  flex-wrap: wrap;
  background-color: rgb(255, 255, 254);
  border: 1px solid gray;
  margin-bottom: 25px;
}
header,main{
  flex: 1 1 51%;
  display: flex;
  align-items: center;
}
header{
  border-bottom: 1px solid gray;
  height: 30px;
  padding-left: 10px;
}
</style>


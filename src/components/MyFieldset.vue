<template>
  <div class="fieldset">
    <hr align="left" width="15px" size="2" color="gray">
    <h3>{{title}}</h3>
    <hr align="right" width="100%" size="2" color="gray">
  </div>
</template>

<script>
export default {
  props: ["title"],
  data() {
    return {};
  }
};
</script>

<style scoped>
.fieldset {
  color: black;
  display: flex;
  overflow: hidden;
  margin-bottom: 15px;
}
h3 {
  font-size: 0.9rem;
  margin: 0px 5px;
}
</style>

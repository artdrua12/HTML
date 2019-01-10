
<template>
  <div class="mycontent">
    <header class="left">

      <div class="ïtem">
        <i class="material-icons first">reorder</i>
      </div>

      <div class="ïtem">
        <md-field>
          <md-select
            v-model="instruments"
            name="instruments"
            id="instruments"
            placeholder="Instruments"
          >
            <md-option value="instruments_one">Instruments_one</md-option>
            <md-option value="instruments_two">Instruments_two</md-option>
            <md-option value="instruments_three">Instruments_three</md-option>
          </md-select>
        </md-field>
      </div>

      <div class="item" v-for="(item,key) in text" :key="key">{{item}}</div>

    </header>
    <header class="right">
      <div class="ïtem">
        <i class="material-icons">account_circle</i>
        <span>Alexander</span>
      </div>
      <div class="ïtem">
        <md-field>
          <md-select v-model="lang" name="lang" id="lang" placeholder="Eng">
            <md-option value="eng">Eng</md-option>
            <md-option value="rus">Rus</md-option>
            <md-option value="other">Other</md-option>
          </md-select>
        </md-field>
      </div>
      <div class="ïtem">
      <i class="material-icons last">lock_open</i>
      </div>
    </header>
    <section>eee</section>
    <main>eeeee</main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      instruments: "",
      lang: "",
      text: ["Widget", "View", "Administration"]
    };
  }
};
</script>

<style scoped>
.mycontent {
  display: flex;
  flex-wrap: wrap;
}
.md-field,
.md-has-placeholder {
  width: 120px;
  min-height: 0px;
}
header.left{
  flex: 3 1 50%;
  justify-content: flex-start;
}
header.right{
  flex: 1 1 250px;
  justify-content: flex-end;
}
div.item {
  display: flex;
  flex: 0 1 150px;
  border: 1px solid black;
}
section {
  flex: 0 1 220px;
  background-color: rgb(226, 231, 235);
  height: calc(100% - 30px);
}
main {
  flex: 1 0 0px;
  background-color: rgb(226, 231, 235);
}
header {
  display: flex;
  background-color: rgb(255, 255, 255);
  height: 45px;
  padding: 0px 2px 0px 12px;
  align-items: center;
  border: 1px solid red;
}
</style>


<template>
  <div class="HContMainLeft">
    <div class="top">
      <div class="img">
        <img src="../assets/picture.png" alt="chart">
      </div>

      <div class="text">
        <p>(Initial): 0 min</p>
        <p>ArMe @ 35 &#176 C Oven</p>
        <p>Out: Ambient Pressure</p>
        <p>25m*320&#956m*1&#956m</p>
      </div>
    </div>
    <div class="center">
      <my-fieldset class="title" title="Control_mode"></my-fieldset>
      <md-checkbox v-model="checkbox" class="md-primary intoMargin">Ok</md-checkbox>
      <div class="flex" v-for="(item,key) in inputArrayCenter" :key="key">
        <p class="half">{{item.title}}</p>
        <input :value="item.value" class="quarter">
        <p class="quarter">{{item.type}}</p>
      </div>
    </div>
    <div class="footer">
      <my-fieldset class="title" title="Post_Run"></my-fieldset>
      <div class="flex" v-for="(item,key) in  inputArrayFooter" :key="key">
        <p class="half">{{item.title}}</p>
        <input :value="item.value" class="quarter" readonly>
        <p class="quarter">{{item.type}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import MyFieldset from "./MyFieldset.vue";
export default {
  data() {
    return {
      checkbox: true,
      inputArrayCenter: [
        { title: "Flow", value: 16.849, type: "mL/min" },
        { title: "Average Velocity", value: 198.05, type: "cm/sec" },
        { title: "Pressure", value: 21.756, type: "psi" },
        { title: "Houdup Time", value: 0.21038, type: "min" }
      ],
      inputArrayFooter: [{ title: "Post Run", value: 16.849, type: "mL/min" }]
    };
  },
  components: {
    MyFieldset
  }
};
</script>

<style scoped>
.HContMainLeft {
  display: flex;
  flex-direction: column;
  background-color: rgb(255, 255, 254);
  border-left: 1px solid gray;
  padding: 12px 12px 0px 12px;
}
.top {
  font-size: 0.8rem;
  overflow: hidden;
  display: flex;
  justify-content: space-around;
}
.text {
  border: 1px solid black;
  padding: 7px;
  float: right;
  margin-right: 15px;
}
.img {
  display: inline-block;
  width: 50%;
}
.title {
  grid-column: 1 / 3;
  grid-row: 1/2;
}
.center {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(47%, 1fr));
  grid-template-rows: auto;
  font-size: 0.8rem;
  margin: 8px 0px;
  overflow: hidden;
}
.md-checkbox{
  margin: 0px 0px 7px 15px;
}
.flex {
  display: flex;
  height: 20px;
  margin: 10px 0px 0px 15px;
  align-items: center
}
.half {
  flex: 1 1 40%;
}
.quarter {
  margin-left: 3px;
  flex: 1 1 20%;
  overflow: hidden;
}
.md-checkbox {
  grid-column: 1 / 3;
  grid-row: 2/3;
}
.footer {
  width: 50%;
  font-size: 0.8rem;
  margin-top: 7px;
}
input {
  width: 60px;
}
</style>

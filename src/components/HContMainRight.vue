<template>
  <div class="HContMainRight">
    <my-fieldset class="title" title="Pleasure/Flow_Setting"></my-fieldset>
    <div class="radioButt">
      <md-radio
        v-for="(item,key) in radioArray"
        :key="key"
        v-model="radio"
        :value="item"
        class="md-primary"
      >{{item}}</md-radio>
    </div>

    <table>
      <tr>
        <th></th>
        <th v-for="(item,key) in tableTitle" :key="key">{{item}}</th>
      </tr>
      <tr v-for="(item,key) in tableData" :key="key">
        <td>
          <md-radio v-if="item.Rate" v-model="radio2" :value="item.Ramp" class="md-primary"></md-radio>
        </td>
        <td>{{item.Ramp}}</td>
        <td>{{item.Rate}}</td>
        <td>{{item.Value}}</td>
        <td>{{item.Hold}}</td>
        <td>{{item.Run_Time}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
import MyFieldset from "./MyFieldset.vue";
export default {
  data() {
    return {
      radio: null,
      radio2: null,
      radioArray: [
        "Constant Preassure",
        "Rampted Preasure",
        "Constant Flow",
        "Ramped Flow"
      ],
      selected: [],
      tableTitle: [
        `Ramp##`,
        `Rate,mL/ min per min`,
        `Value, mL/min`,
        `Hot Time,min`,
        `Run Time.min`
      ],
      tableData: [
        {
          Ramp: "(initial)",
          Rate: null,
          Value: 16.849,
          Hold: null,
          Run_Time: null
        },
        {
          Ramp: "Ramp 1",
          Rate: 10,
          Value: 16.849,
          Hold: 0,
          Run_Time: 0
        },
        {
          Ramp: "Ramp 2",
          Rate: 10,
          Value: 16.849,
          Hold: 0,
          Run_Time: 0
        }
      ]
    };
  },
  components: {
    MyFieldset
  }
};
</script>

<style scoped>
.HContMainRight {
  display: flex;
  flex-direction: column;
  background-color: rgb(255, 255, 254);
  border-left: 1px solid gray;
}
.title {
  padding: 0px 12px;
}
.radioButt {
  display: flex;
  justify-content: center;
  font-size: 12px;
  width: 80%;
}
.center {
  text-align: center;
}
.md-radio {
  margin: 0px;
}
div.table {
  width: 100%;
  overflow: auto;
  font-size: 14px;
}
table {
  width: 100%; /* Ширина таблицы */
  border-collapse: collapse; /* Отображать только одинарные линии */
  text-align: right;
  margin-top: 20px;
  font-size: 14px;
}
th {
  background-color: #448aff;
  color: white;
  text-align: center;
  padding: 7px 2px;
  font-size: 13px;
  vertical-align: middle;
}
td {
  border: 2px solid rgb(173, 167, 167);
  padding: 5px 10px 0px 10px;
  height: 30px;
  vertical-align: middle;
}

td:first-child {
  border-left: none;
}

td:last-child {
  border-right: none;
}
</style>

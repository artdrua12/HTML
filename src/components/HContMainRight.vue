<template>
  <div class="HContMainRight">
    <my-fieldset class="title" title="Pleasure/Flow_Setting"></my-fieldset>
    <div class="radioButt">
      <template v-for="(item,key) in radioArray">
        <input :key="key" :id="item" type="radio" name="gender" :value="item">
        <label :key="key" :for="item">{{item}}</label>
      </template>
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
  padding: 12px;
}

.md-radio {
  margin: 0px;
}

div.radioButt {
  display: flex;
  justify-content: center;
  font-size: 12px;
  padding: 7px 0px;
}

table {
  width: 100%; /* Ширина таблицы */
  border-collapse: collapse; /* Отображать только одинарные линии */
  text-align: right;
  margin-top: 20px;
  font-size: 13px;
}
th {
  background-color: #448aff;
  color: white;
  text-align: center;
  padding: 7px 2px;
  vertical-align: middle;
}
td {
  border: 1px solid rgb(173, 167, 167);
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
tr:hover {
  background-color: #c6d5f0;
}
label {
  display: inline-block;
  cursor: pointer;
  position: relative;
  padding-left: 20px;
  margin-right: 10px;
  font-size: 12px;
}
input[type="radio"] {
  display: none;
}
label:before {
  content: "";
  display: inline-block;
  width: 16px;
  height: 16px;
  position: absolute;
  left: 0;
  bottom: 1px;
  border: 1px solid gray;
}
label:before {
  border-radius: 10px;
}
input[type="radio"]:checked + label:before {
  content: "\2022";
  color: #f3f3f3;
  font-size: 30px;
  text-align: center;
  line-height: 17px;
  background-color: #448aff;
}
</style>

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
    <div class="table">
      <!-- <tr>
        <th></th>
        <th v-for="(item,key) in tableTitle" :key="key">{{item}}</th>
      </tr>
      <tr v-for="(item,key) in tableData" :key="key">
        <td><md-radio v-if="item.Rate" v-model="radio2" :value="item.Ramp" class="md-primary"></md-radio></td>
        <td>{{item.Ramp}}</td>
        <td>{{item.Rate}}</td>
        <td>{{item.Value}}</td>
        <td>{{item.Hold}}</td>
        <td>{{item.Run_Time}}</td>
      </tr>-->
      <md-table md-card>
        <md-table-row>
          <md-table-head></md-table-head>
          <md-table-head v-for="(item,key) in tableTitle" :key="key">{{item}}</md-table-head>
        </md-table-row>

        <md-table-row v-for="(item,key) in tableData" :key="key">
          <md-table-cell>
            <md-radio v-if="item.Rate" v-model="radio2" :value="item.Ramp" class="md-primary"></md-radio>
          </md-table-cell>
          <md-table-cell>{{item.Ramp}}</md-table-cell>
          <md-table-cell>{{item.Rate}}</md-table-cell>
          <md-table-cell>{{item.Value}}</md-table-cell>
          <md-table-cell>{{item.Hold}}</md-table-cell>
          <md-table-cell>{{item.Hold}}</md-table-cell>
        </md-table-row>
      </md-table>
    </div>
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
        `Rate,mL/min per min`,
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
          Ramp: "Ramp1",
          Rate: 10,
          Value: 16.849,
          Hold: 0,
          Run_Time: 0
        },
        {
          Ramp: "Ramp2",
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
  padding: 10px;
  width: 100%;
}
.radioButt {
  display: flex;
  justify-content: center;
  font-size: 12px;
  width: 80%;
}
div.table {
  overflow: auto;
  font-size: 14px;
}
table {
  width: 100%; /* Ширина таблицы */
  border: 4px double black; /* Рамка вокруг таблицы */
  border-collapse: collapse; /* Отображать только одинарные линии */
}
th,
td {
  border: 1px solid gray;
  height: 10px;
  width: 
}
th {
  background-color: #448aff;
  color: white;
}
</style>

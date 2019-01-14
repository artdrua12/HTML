<template>
  <div class="HContMainRight">
    <my-fieldset  class="title" title="Pleasure/Flow_Setting"></my-fieldset>
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
      <md-table v-model="people" >

        <md-table-toolbar slot="md-table-alternate-header" slot-scope="{ count }">
          <div class="md-toolbar-section-start">{{ getAlternateLabel(count) }}</div>

          <div class="md-toolbar-section-end">
            <md-button class="md-icon-button">
              <md-icon>delete</md-icon>
            </md-button>
          </div>
        </md-table-toolbar>

        <md-table-row
          slot="md-table-row"
          slot-scope="{ item }"
          :md-disabled="item.name.includes('Stave')"
          md-selectable="multiple"
          md-auto-select
        >
          <md-table-cell md-label="Name" md-sort-by="name">{{ item.name }}</md-table-cell>
          <md-table-cell md-label="Email" md-sort-by="email">{{ item.email }}</md-table-cell>
          <md-table-cell md-label="Gender" md-sort-by="gender">{{ item.gender }}</md-table-cell>
          <md-table-cell md-label="Job Title" md-sort-by="title">{{ item.title }}</md-table-cell>
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
      radioArray: [
        "Constant Preassure",
        "Rampted Preasure",
        "Constant Flow",
        "Ramped Flow"
      ],
      selected: [],
      people: [
        {
          name: "Shawna Dubbin",
          email: "sdubbin0@geocities.com",
          gender: "Male",
          title: "Assistant Media Planner"
        },
        {
          name: "Odette Demageard",
          email: "odemageard1@spotify.com",
          gender: "Female",
          title: "Account Coordinator"
        },
        {
          name: "Lonnie Izkovitz",
          email: "lizkovitz3@youtu.be",
          gender: "Female",
          title: "Operator"
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
.title{
    margin: 12px 12px 2px 12px
}
.radioButt {
  display: flex;
  justify-content:center;
  font-size: 9px;
}
.table{
    overflow: auto;
    font-size: 9px;
}


</style>


<template>
  <div class="mysidebar">
    <header>LIMS</header>
    <article class="search">
      <md-field>
        <label>Search</label>
        <md-input v-model="text"></md-input>
        <md-icon>search</md-icon>
      </md-field>
    </article>
    <article class="animation">
      <md-progress-bar class="md-accent" md-mode="determinate" :md-value="amount"></md-progress-bar>
    </article>
    <footer>
      <span>RUN</span>
      <md-button
        class="md-icon-button"
        :class="{ on: !isDisabled }"
        @click="run"
        :disabled="isDisabled"
      >On</md-button>
      <md-button
        class="md-icon-button"
        :class="{ off: isDisabled }"
        @click="stop"
        :disabled="!isDisabled"
      >Off</md-button>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: "",
      amount: 10,
      isDisabled: false,
      timer: ""
    };
  },
  methods: {
    run() {
      this.isDisabled = !this.isDisabled;

      this.timer = setInterval(() => {
        if (this.amount >= 100) {
          this.amount = 0;
        }
        this.amount += 10;
        console.log("tick")
      }, 500);
    },
    stop() {
      this.isDisabled = !this.isDisabled;
      clearInterval(this.timer);
    }
  }
};
</script>

<style scoped>
div.mysidebar {
  width: 100%;
  height: 100%;
  background-color: rgb(197, 206, 211);
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(2, auto) 1fr repeat(2, auto);
  overflow: hidden;
}
.search {
  grid-column: 1 / 2;
  grid-row: 3 / 4;
  height: 45px;
  display: flex;
}
.animation {
  grid-column: 1 / 2;
  grid-row: 6 / 7;
}
.md-icon {
  right: 20px;
  top: -5px;
}
.md-accent {
  height: 20px;
}
.md-icon-button {
  color: white;
  border: 3px solid rgb(238, 245, 238);
}
.on {
  border-top: 7px solid rgb(23, 228, 23);
}
.off {
  border-top: 7px solid rgb(247, 201, 76);
}
header,
footer {
  padding: 10px 20px 9px 27px;
  font-size: 1.5rem;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  color: white;
  letter-spacing: 3px;
}

header {
  grid-column: 1 / 2;
  grid-row: 1 / 2;
  background-color: rgb(39, 39, 51);
}
footer {
  grid-column: 1 / 2;
  grid-row: 7 / 8;
  align-self: flex-end;
  background-color: rgb(36, 99, 158);
  display: flex;
  justify-content: flex-end;
}

label {
  left: 20px;
  top: 15px;
  font-size: 1.1rem;
}

span {
  margin-right: 100px;
}
</style>


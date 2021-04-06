<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <hr />
    <p>Counter Value: <small-component :counter="counter" /></p>
    <button @click="decrement(2)">- 1</button>
    <button @click="reset">Reset</button>
    <button @click="increment(2)">+ 1</button>
    <hr />
    <button @click="show = !show">Show</button>
    <span> Show/Hide {{ JSON.stringify(show) }} </span>
    <hr />
    <div class="result">
      <h2>Log</h2>
    </div>
  </div>
</template>

<script>
import SmallComponent from "./SmallComponent.vue";
import HardProcess from "./../helpers/HardProcess.js";

export default {
  components: { SmallComponent },
  name: "HelloWorld",
  data: function () {
    return {
      counter: 10,
      show: false,
      myClass: new HardProcess(),
    };
  },
  props: {
    msg: String,
  },
  methods: {
    increment: function (op = 1) {
      this.counter += op;
    },
    decrement: function (op = 1) {
      this.counter -= op;
    },
    reset: function () {
      this.counter = 10;
    },
  },
  mounted: function () {
    this.myClass.callProcess(this.counter);
  },
  watch: {
    counter: function (val) {
      this.myClass.callProcess(val);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
button {
  margin: 4px;
  padding-left: 20px;
  padding-right: 20px;
  padding-bottom: 6px;
  padding-top: 6px;
}

.container {
  width: 1000px;
  margin: 0 auto;
}
</style>

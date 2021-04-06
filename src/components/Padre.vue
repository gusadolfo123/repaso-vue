<template>
  <div className="container">
    <h1>Padre</h1>
    <p>Total: {{ valor }}</p>
    <hr />
    <Hijo
      v-for="numero in numeros"
      :key="numero"
      :numero="numero"
      :incrementar="incrementar"
    />
  </div>
</template>

<script>
import Hijo from "./Hijo.vue";

export default {
  name: "Padre",
  components: {
    Hijo,
  },
  data: function () {
    return {
      valor: 0,
      numeros: [2, 4, 6, 8, 10],
    };
  },
  methods: {
    incrementar: function (val) {
      this.valor += val;
    },
  },
};
</script>

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


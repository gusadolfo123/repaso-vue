<template>
  <button className="btn btn-primary mr-3" @click="incrementar(numero)">
    {{ numero }}
  </button>
</template>

<script>
export default {
  name: "Hijo",
  props: ["numero", "incrementar"],
};
</script>

<style scoped>
button {
  margin: 4px;
  padding-left: 20px;
  padding-right: 20px;
  padding-bottom: 6px;
  padding-top: 6px;
}
</style>
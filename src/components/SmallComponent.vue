<template>
  <div class="counter">
      <small>{{ counter }}</small>
  </div>
</template>

<script>
export default {
    name: "SmallComponent",
    props: ['counter'],
    mounted: function(){
      console.log("Entro");
    }
}
</script>


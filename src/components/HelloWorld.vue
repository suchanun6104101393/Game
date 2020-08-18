<template>
  <div class="hello">
    <button @click="randomDamage(1,10)" class="btn btn-successml-3">Start {{randomDamage(1,10)}}</button>
  

    <p v-bind:style="{fontSize: fsize + 'px'}">{{counter}}</p>
 
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      counter: 0,
      fsize: 50,
      randomNo: 0,
 
    };
  },
  props: {
    lable: String,
  },
  methods: {
     randomDamage: function(min, max) {
 return Math.max(Math.floor(Math.random() * max) + 1, min);
 },
  },
};
</script>
<style>
</style>
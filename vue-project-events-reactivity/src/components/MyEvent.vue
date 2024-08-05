<script setup>
import {ref} from 'vue';

let count = ref(0)
let increementCounter = () => {count.value++;};
let decreementCounter = () => {count.value--;};
</script>

<template>
  <h1>Count: {{count}}</h1>
  <button v-on:click="increementCounter">Increement</button>
  <button @:click="decreementCounter">Decreement</button>
</template>

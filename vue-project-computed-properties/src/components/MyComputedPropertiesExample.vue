<script setup>
import { ref, computed } from 'vue';
let count = ref(0);
let square = computed(()=>count.value**2)
</script>

<template>
<h1>Count : {{count}}</h1>
<h1>Square: {{square}}</h1>
<button @:click="count++">Increment</button>
</template>
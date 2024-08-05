<script setup>
import { ref } from 'vue';
let isVisible = ref(true);

</script>

<template>

<h1>User Profile:</h1>
<h2 v-show="isVisible">Name: Kaushal Agarwal</h2>
<h2 v-show="isVisible">Age: 27</h2>
<button @:click="isVisible = !isVisible">Hide Details</button>
</template>
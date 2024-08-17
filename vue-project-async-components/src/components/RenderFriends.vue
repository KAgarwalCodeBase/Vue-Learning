<script setup>
import {ref} from 'vue';
let friends = ref(['Spiderman', 'IronMan', 'Captain America', 'Wonder Women']);


</script>

<template>
    <h3 v-for="(friend, ind) in friends" :key="ind">{{friend}}</h3>
</template>
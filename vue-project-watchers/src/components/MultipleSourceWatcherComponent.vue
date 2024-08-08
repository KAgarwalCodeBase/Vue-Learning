<script setup>
import {ref, watch} from 'vue';
let username = ref('Jordan');
let counter = ref(0);
let incrementCount = ()=> counter.value++;
let changeName=()=> username.value!='Alex'? username.value='Alex':
        username.value='Jordan';
watch([username, counter], (newValue, oldValue)=>{
    console.log('New Value: ', newValue);
    console.log('old Value: ', oldValue);
})
</script>

<template>
    <h2>Name: {{username}}</h2>
    <button @click="incrementCount">increment count</button>
    <br> <br>
    <button @click="changeName">Change Name</button>
</template>
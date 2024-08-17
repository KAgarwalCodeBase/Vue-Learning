<script setup>
    import {onMounted} from 'vue';
    let myRef;
    onMounted(()=>{
        console.log(myRef);
        myRef.focus();
        myRef.value = 'Kaushal Agarwal';
    })
</script>

<template>
    <h1>Basic ref example.</h1>
    <input type="text" ref="myRef">
</template>
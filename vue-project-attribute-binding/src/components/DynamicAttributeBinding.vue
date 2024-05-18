<script setup>
const imgInfo ={
    src : "https://images.unsplash.com/photo-1715966966827-25a227141ee9?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
    alt: 'This is random image.',
    width: 400,
    height: 400
}
</script>
<template>
    <h1>Inside the dynamic attribute binding.</h1>
    <img :="imgInfo">
</template>

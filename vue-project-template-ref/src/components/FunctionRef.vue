<script setup>
const myRefFun = (el)=>{
    console.log(el.textContent);
    el.textContent = "Text Changed";
    el.style.color = "crimson"
    console.log(el.textContent);
}
</script>
<template>
    <h1 :ref="myRefFun">This is initial value.</h1>
</template>
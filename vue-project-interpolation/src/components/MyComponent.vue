<script setup>
var firstname = "Kaushal";
var lastname = "Agarwal";
function add (x,y){
    return x+y;
}

</script>
<template>
<h1>{{firstname +" "+ lastname }}</h1>
<h2>Add Two numbers: {{add(2,4)}}</h2>
</template>
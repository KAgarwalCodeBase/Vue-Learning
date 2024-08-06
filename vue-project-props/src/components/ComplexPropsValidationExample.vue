<script setup>
    defineProps({
        fullname:{
            type:String,
            required:true
        },
        age:{
            type:Number,
            required:false
        }
    })
</script>

<template>
    <h2>Fullname: {{fullname}}</h2>
    <h2>Age: {{age}}</h2>
</template>
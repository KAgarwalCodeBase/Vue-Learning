<script setup>
    let props = defineProps({
        fullname: String,
        age: Number
    })
</script>

<template>
    <h2>Fullname: {{props.fullname}}</h2>
    <h2>Age: {{props.age}}</h2>
</template>
<script setup>
    let props = defineProps(['name'])
</script>

<template>
    <h2>Name: {{props.name}}</h2>
</template>
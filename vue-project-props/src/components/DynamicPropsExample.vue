<script setup>
    let props = defineProps(['counter'])
    // Props are "immutable" that means there value cannot be changed
    // They are just readonly.
    // props.counter=10; //It does not work it will give a warning at console.
</script>

<template>
    <h2>Counter: {{counter}}</h2>
</template>
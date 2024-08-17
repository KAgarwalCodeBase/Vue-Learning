<script setup>
    import { useCounter } from '@/shared/useCounter';
    const counter = useCounter()
</script>


<template>
    <h2>Count: {{counter.count}}</h2>
    <button @click="counter.increment">+</button>
    <button @click="counter.decrement">-</button>
</template>
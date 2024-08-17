<script setup>
import {ref} from 'vue';
let count = ref(10);
let increment = () =>count.value++
let decrement = () => count.value--

/*
    When using the <script setup>
    It's private by default.
    A parent referencing a child won't able to access anything.

    First we have to expose all the properties and methods
    then we'd able to use them in parent component.
    use (defineExpose) to expose our data for parent to use.
*/

defineExpose({count, increment, decrement})
</script>
<template>
    <h1>Count: {{ count }}</h1>
    <button v-on:click="increment">Increment</button>
    <br><br>
    <button @:click="decrement">Decrement</button>

</template>

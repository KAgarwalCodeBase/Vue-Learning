<script setup>
    defineProps({
        book:Object,
        petNames:Array
    })
</script>

<template>
    <h2>Book Details:</h2>
    <li v-for="(c, i) in book" :key="i">{{c}}</li>
    <h2>Pet Names:</h2>
    <li v-for="(c,i) in petNames" :key="i">{{c}}</li>
</template>
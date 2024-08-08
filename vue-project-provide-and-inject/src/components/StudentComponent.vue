<script setup>
    import {inject} from 'vue';
    const studentName = inject('studentName');
    const studentEmail = inject('studentEmail');
    const studentRollNumber = inject('studentRollNumber'); 
</script>
<template>
    <h1>Name: {{ studentName }}</h1>
    <h1>Email: {{ studentEmail }}</h1>
    <h1>Roll Number: {{ studentRollNumber }}</h1>
</template>
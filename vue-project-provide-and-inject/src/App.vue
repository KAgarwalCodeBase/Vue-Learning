<script setup>
  import {provide} from 'vue';
  import SchoolComponent from './components/SchoolComponent.vue';
  provide('studentName', 'Kaushal Agarwal');
  provide('studentEmail', 'Kaushal@gmail.com');
  provide('studentRollNumber', 11);
</script>
<template>
  <SchoolComponent/>
</template>
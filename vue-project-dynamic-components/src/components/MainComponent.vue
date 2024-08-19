<script setup>
    import { ref } from 'vue';
    import ComponentOne from './ComponentOne.vue';
    import ComponentTwo from './ComponentTwo.vue';
    import ComponentThree from './ComponentThree.vue';
    let currentTab = ref('ComponentOne');
    let tab = {
        ComponentOne,
        ComponentTwo,
        ComponentThree
    }
</script>

<template>
    <button @click="currentTab='ComponentOne'">What is HTML?</button>
    <button @click="currentTab='ComponentTwo'">What is CSS?</button>
    <button @click="currentTab='ComponentThree'">What is Javascript?</button>
    
    <!-- Dynamic Component -->
    <component :is="tab[currentTab]"/>
</template>
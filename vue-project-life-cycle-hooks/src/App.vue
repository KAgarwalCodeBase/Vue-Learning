<script setup>
    import {ref} from 'vue';
    import LifeCycleComponent from './components/LifeCycleComponent.vue';
    let showHide = ref(false)
</script>


<template>
    <LifeCycleComponent v-if="showHide"/>
    <button @click="showHide=!showHide">Show/Hide</button>
</template>
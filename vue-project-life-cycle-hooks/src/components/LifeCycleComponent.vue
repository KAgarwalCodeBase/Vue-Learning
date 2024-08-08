<script setup>
    import {
        ref,
        onBeforeMount,
        onMounted,
        onBeforeUpdate,
        onUpdated,
        onBeforeUnmount,
        onUnmounted
    } from 'vue';

    onBeforeMount(()=>{
        console.log('Component is about to be mounted');
    })

    onMounted(()=>{
        console.log('Component is has been mounted');
    })

    onBeforeUpdate(()=>{
        console.log('Component is about to update');
    })

    onUpdated(()=>{
        console.log('Component has been Updated.');
    })

    onBeforeUnmount(()=>{
        console.log('Component is about to unmounted');
    })

    onUnmounted(()=>{
        console.log('Component has been unmounted');
    })

    const message = ref('Hello World');
    const updateMessage = ()=>{
        message.value = 'Updated Value!';
    }
</script>

<template>
    <p>{{message}}</p>
    <button @:click="updateMessage">Update Message</button>
</template>
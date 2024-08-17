<script setup>
    // import RenderFriends from './RenderFriends.vue';
    import {ref, defineAsyncComponent} from 'vue';
    const RenderFriends = defineAsyncComponent(()=>{
        import('./RenderFriends.vue')
    })
    let showFriends =  ref(false)
    const toggleFriends = ()=>{showFriends.value=!showFriends.value}
</script>

<template>
    <div v-if="showFriends">
        <RenderFriends/>
    </div>
    <button @:click="toggleFriends">Toggle Friends</button>
</template>
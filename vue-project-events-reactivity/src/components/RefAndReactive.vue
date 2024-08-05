<script setup>
import {reactive, ref} from 'vue';
let friendLists = reactive([ref('Jordan'), ref('Alex'), ref('King')])
</script>

<template>
    <h1>1. {{friendLists[0]}}</h1>
    <h1>2. {{friendLists[1]}}</h1>
    <h1>3. {{friendLists[2]}}</h1>

    <button @:click="friendLists[0]='🤝'">Hand Shake</button>
    <button @:click="friendLists[1]='🤝'">Hand Shake</button>
    <button @:click="friendLists[2]='🤝'">Hand Shake</button>
    
</template>
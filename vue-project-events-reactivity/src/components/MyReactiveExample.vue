<script setup>
import { reactive } from 'vue';

let initialState = reactive({val: {count: 0}, user: ["King", "Kaushal"]})
let changeUser = ()=> {
    initialState.user[0] = "Wondar",
    initialState.user[1] = "Women"
}

</script>

<template>
 <h1> Current Count: {{initialState.val.count}}</h1>
<h1>Users:  {{initialState.user}}</h1>
<button @:click="initialState.val.count+=10">Add 10</button>
<button @:click="initialState.val.count-=10">Substract 10</button>
<button @:click="changeUser"> Change User </button>
<button @:click="initialState.user.push('Super Man')">Add User</button>
</template>
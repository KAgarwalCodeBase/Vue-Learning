<script setup>
import { ref } from 'vue';
// using ref for primitive value.
let username = ref('');
// using ref for arrays.
let userList = ref(['Michel', 'Jordan', 'Super', 'Man'])
// using ref for objects.
let userInfo = ref({
    name: 'Salman Khan',
    profession: 'actor',
    age: 50,
    isMarried: false
})

</script>

<template>
<h1>Username : {{username}}</h1>
<button @:click="username='Jordan'"> Add Username</button>
<h1>UserList: {{userList}}</h1>
<button @:click="userList.push('Batman')">Add User</button>
<h1>Name: {{userInfo.name}}</h1>
<h1>Age: {{userInfo.age}}</h1>
<h1>IsMarries: {{userInfo.isMarried}}</h1>
<h1>Profession: {{userInfo.profession}}</h1>
<button @:click="userInfo.name='Amitab Bachan'">Change name</button>
</template>
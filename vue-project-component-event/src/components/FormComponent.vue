<script setup>
    import { ref } from 'vue'; 
    let userInfo = ref({
        username:"",
        email:"",
        password:""
    })
</script>

<template>
    <form @submit.prevent="$emit('getUserInfo',userInfo)" >
        <input type="text" placeholder="username" v-model="userInfo.username"> <br>
        <input type="email" placeholder="email" v-model="userInfo.email"><br>
        <input type="password" placeholder="password" v-model="userInfo.password">
        <button @click="submit">Submit</button>
    </form>
</template>
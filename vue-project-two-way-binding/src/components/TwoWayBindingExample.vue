<script setup>
    import { ref } from 'vue';
    let formData = ref({
        username: '',
        email: '',
        password:''
    })
</script>

<template>
    <form @submit.prevent>
        <input type="text" placeholder="Please enter your username." v-model="formData.username"><br/><br/>
        <input type="email" placeholder="Please enter your email." v-model="formData.email"><br/><br/>
        <input type="password" placeholder="Please enter your password." v-model="formData.password"><br/><br/>
        <button type="submit">Submit</button>
    </form>
    <h1>{{formData.username}}</h1>
    <h1>{{formData.email}}</h1>
    <h1>{{formData.password}}</h1>
</template>
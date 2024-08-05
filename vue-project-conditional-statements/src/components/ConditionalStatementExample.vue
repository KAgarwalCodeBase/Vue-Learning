<script setup>
let isAuthorized = false
let userInfo = {
    name: "Super Man",
    profession: "Super Hero",
    age: "50",
    address: "DC Universe"
}
</script>

<template>
    <h1>User Info:</h1>
    <h1>Name: {{userInfo.name}}</h1>
    <h1>Profession: {{userInfo.profession}}</h1>
    <div v-if="isAuthorized">
        <h1>Age: {{userInfo.age}}</h1>
        <h1>Address: {{userInfo.address}}</h1>
    </div>
    <div v-else> 
        <h1>Do Login to see complete info.</h1>
    </div>
</template>
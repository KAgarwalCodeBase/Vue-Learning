<script setup>
    let submitHandler = (e)=>{
        e.preventDefault();
        alert("Valid Credentials");
    }
</script>
<template>
<form @:submit="submitHandler">
    <input type="text" placeholder="Please Enter Your Name">
    <input type="email" placeholder="Please Enter Your Email">
    <button type="submit">Submit</button>
</form>
</template>

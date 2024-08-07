<script setup>
  import FormComponent from './components/FormComponent.vue';
  const formHandler = (userInfo)=>{
    console.log(userInfo);
  }
</script>

<template>
  <FormComponent @getUserInfo="formHandler"/>
</template>
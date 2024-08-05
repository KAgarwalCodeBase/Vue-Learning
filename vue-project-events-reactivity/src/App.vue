<script setup>
import MyEvent from './components/MyEvent.vue';
import MyForm from './components/MyForm.vue';
import MyReactiveExample from './components/MyReactiveExample.vue';
import MyRefExample from './components/MyRefExample.vue';
import RefAndReactive from './components/RefAndReactive.vue';
</script>

<template>
 <h1>Example Of Events: </h1>
 <MyEvent/>
 <br><br>
 <h1>Example of Forms: </h1>
 <MyForm/>
 <br><br>
 <h1>Example of reactive(): </h1>
 <MyReactiveExample/>

 <br><br>
 <h1>Example of ref(): </h1>
 <MyRefExample/>
 
 <br><br>
 <h1>Example of using ref inside reactive: </h1>
 <RefAndReactive/>
  
</template>

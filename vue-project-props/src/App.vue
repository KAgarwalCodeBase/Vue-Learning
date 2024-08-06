<script setup>
import { ref } from 'vue';
import StaticPropsExample from './components/StaticPropsExample.vue';
import DynamicPropsExample from './components/DynamicPropsExample.vue';
import PropsValidationExample from './components/PropsValidationExample.vue';
import ComplexPropsValidationExample from './components/ComplexPropsValidationExample.vue';
import ComplexObjectInPropsExample from './components/ComplexObjectInPropsExample.vue';
import CustomValidatorPropsExample from './components/CustomValidatorPropsExample.vue';
let book = {
        "title": "To Kill a Mockingbird",
        "author": "Harper Lee",
        "year": 1960,
        "genre": "Fiction",
        "ISBN": "978-0061120084"
    }
let petNames = [
    "Bella",
    "Charlie",
    "Max",
    "Luna"]
let counter = ref(0);

let userInfo = {fullname:"Kaushal Agarwal", age: 27};
</script>

<template>
<h1>Static Props Example.</h1>
<StaticPropsExample name="Kaushal Agarwal"/>
<hr>
<h1>Dynamic Props Example.</h1>
<DynamicPropsExample :counter="counter"/>
<button @click="counter++">Add value</button>
<hr>
<h1>Props Validation Example.</h1>
<PropsValidationExample :fullname="userInfo.fullname" :age="userInfo.age"/>
<hr>
<h1>Complex Props Validation Example.</h1>
<ComplexPropsValidationExample  :age="userInfo.age"/>
<hr>
<h1>Complex Objects In Props Example.</h1>
<ComplexObjectInPropsExample :book="book" :petNames="petNames"/>
<hr>
<CustomValidatorPropsExample name="IronMan" age=27 password="impossiblePassword"/>
</template>


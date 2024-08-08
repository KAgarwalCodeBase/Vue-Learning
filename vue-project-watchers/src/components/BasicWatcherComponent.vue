<script setup>
import {reactive, ref, watch} from 'vue';
let message = ref('Hello World!');
let userInfo = reactive({username: 'Jordan'});
// Here we cann't provide an specific property of object.
// We have to provide entire object, otherwise it's gonna give us error in the console.

// Now if we want to get the "old" & the "new" values separately, 
// - for that we'll have to pass a getter function.
// - & here we have to specify the actual object/state "property"
watch(() => userInfo.username, (newValue, oldValue)=>{
    message.value = newValue.username;
    console.log('Old Value: ', oldValue);
    console.log('New Value: ', newValue);
})
</script>
<template>
    {{ message }} <br><br>
    <input type="text" v-model="userInfo.username" placeholder="name">
</template>


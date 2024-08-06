<script setup>
    defineProps({
        name:{
            type:String,
            validator: (propValue)=>{
                return ['SuperMan', 'BatMan', 'SpiderMan'].includes(propValue)
            }
        },
        age:{
            type:Number,
            validator: (propValue)=>(propValue>=18 && propValue<=30 ? true : false)
        },
        password:{
            type:String,
            validator: (propValue)=>(propValue.length>=8)
        }
    })
</script>

<template>
    <h2>{{name}}</h2>
    <h2>{{age}}</h2>
    <h2>{{password}}</h2>
</template>
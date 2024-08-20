<script setup>
    import {ref} from 'vue';
    let data = ref(null);
    const fetchData = ()=>{
        fetch('https://jsonplaceholder.typicode.com/todos/1')
        .then((response)=>{
            if(!response.ok){
                throw Error(`Http Error: Status ${response.status}`)
            }
            return response.json()
        })
        .then((responseData)=>{
            data.value = responseData
        })
        .catch((error)=>{
            console.error(`Error Fetching Data: ${error}`)
        })
    }
</script>

<template>
    <h1>(( Data From API))</h1>
    <pre>{{ data.value}}</pre>
    <button @click="fetchData">Fetch Data</button>
</template>
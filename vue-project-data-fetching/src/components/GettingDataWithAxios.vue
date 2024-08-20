<script setup>
    import axios from 'axios';
    import { ref } from 'vue';
    let data = ref(null);
    const fetchData =  async () =>{
        try{
            // Make a get request using axios.
            const response = await axios.get('https://jsonplaceholder.typicode.com/todos/1');
            console.log('Logging response')
            console.log(response)

            // Handle the successful response
            data.value = response.data
        }catch(error){
            console.error(`Error Fetching Data: ${error}`)
        }
    }
</script>
<template>
    <h1>(( Using Axios ))</h1>
    <button @click="fetchData">Fetch Data</button>
    <div>
        <h2>Data From API:</h2>
        <pre>{{data}}</pre>
    </div>
</template>
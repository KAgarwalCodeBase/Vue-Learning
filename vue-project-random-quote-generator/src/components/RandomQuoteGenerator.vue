<script setup>
    import { ref, onMounted } from 'vue';
    let quotes = ref([
        {
            "text": "The only limit to our realization of tomorrow is our doubts of today.",
            "author": "Franklin D. Roosevelt"
        },
        {
            "text": "The purpose of our lives is to be happy.",
            "author": "Dalai Lama"
        },
        {
            "text": "Life is what happens when you're busy making other plans.",
            "author": "John Lennon"
        },
        {
            "text": "Get busy living or get busy dying.",
            "author": "Stephen King"
        },
        {
            "text": "You only live once, but if you do it right, once is enough.",
            "author": "Mae West"
        },
        {
            "text": "In the end, we will remember not the words of our enemies, but the silence of our friends.",
            "author": "Martin Luther King Jr."
        },
        {
            "text": "The best way to predict the future is to invent it.",
            "author": "Alan Kay"
        },
        {
            "text": "To be yourself in a world that is constantly trying to make you something else is the greatest accomplishment.",
            "author": "Ralph Waldo Emerson"
        }
    ]
    )
    const currentQuote = ref({text:'', author:''})
    const getRandomQuote = ()=>{
        const randomIndex = Math.floor(Math.random()*quotes.value.length);
        currentQuote.value = quotes.value[randomIndex];
    }
    onMounted(getRandomQuote);
</script>
<template>
    <div class="quote-generator">
        <h1 class="app-title">Random Quote Generator</h1>
        <blockquote class="quote-container">
            <p>{{currentQuote.text}}</p>
            <cite>{{currentQuote.author}}</cite>
        </blockquote>
        <button @click="getRandomQuote" class="quote-button">Get Random</button>
    </div>
</template>

<style scoped>
.quote-generator{
  max-width: 400px;
  margin: 50px auto;
  padding: 20px;
  text-align: center;
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0 ,0.1);
}
.app-title {
  font-size: 24px;
  margin-bottom: 20px;
  color: #333;
}

.quote-container {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 8px;
  border: 1px solid #ddd;
  margin-bottom: 20px;
}

p {
  font-size: 18px;
  margin-bottom: 10px;
}

cite {
  font-style: normal;
  color: #777;
}

.quote-button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #3498db;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.quote-button:hover {
  background-color: #2980b9;
}
</style>
<script setup>
let books = [
    {
        "title": "To Kill a Mockingbird",
        "author": "Harper Lee",
        "year": 1960,
        "genre": "Fiction",
        "ISBN": "978-0061120084"
    },
    {
        "title": "1984",
        "author": "George Orwell",
        "year": 1949,
        "genre": "Dystopian",
        "ISBN": "978-0451524935"
    }
]

</script>
<template>
<h1>This is an iteration example.</h1>
<div v-for="({title, author, year, genre, ISBN}, i) in books" :key="index">
    <h3>Title: {{ title }}</h3>
    <h3>Author: {{ author }}</h3>
    <h3>Year: {{ year }}</h3>
    <h3>Genre: {{ genre }}</h3>
    <h3>ISBN: {{ ISBN }}</h3>
    <hr>
</div>
</template>
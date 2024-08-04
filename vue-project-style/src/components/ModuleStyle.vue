<template>
<h1 v-bind:class="$style['m-class']"> This is module example.</h1>
<h1 :class="$style['l-class']"> This is another module example.</h1>
</template>


<style module>
.m-class {
    background: firebrick;
    color: white;
}
.l-class {
    background: green;
    color: white;
}
</style>

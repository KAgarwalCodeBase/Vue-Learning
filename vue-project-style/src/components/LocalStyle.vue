<script setup>
const mychannel = "https://www.youtube.com/watch?v=aBFv3f6jq0k";
</script>

<template>
    <!-- <h1 class="text-red">Local Style.</h1>
    <p class="local">This is a local style.</p>
    <p class="g-1">This is the global style.</p> -->
    <a :href="mychannel"> My Channel</a>
</template>

<style scoped>
.local{
    color:green;
}
</style>
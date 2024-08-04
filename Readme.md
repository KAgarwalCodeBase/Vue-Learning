<h3>Command to do new Project Setup</h3>

<i>npm create vue@latest</i> </br>
<i>project-name: vue-course (exmaple name)</i></br>
<i>cd vue-course</i></br>
<i>npm install</i></br>
<i>npm run format</i></br>
<i>npm run dev</i></br>

Component - Building blocks of Single Page Applications.

Interpolation {{ }} - Dynamically Binding Data to the content of an HTML element.

Attribute Binding & Dynamic Attribute Binding  :attr or v-bind:attr - 
    It is a way to bind HTML attributes to data in Vue Instance.
    
example:

<code>

    <script setup>
        const mychannel = "https://www.youtube.com/channel/UCbBS5Mp6r9lB9-o8Hn1YMRw";
        const amazingImage = "https://images.unsplash.com/photo-1715966966827-25a227141ee9?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D";
        const altText = "This is some image";
        const imageWidth = 400;
        const imageHeight = 400;
    </script>

    <template>
        <h1>Inside the attribute binding.</h1>
        <a :href="mychannel">My Channel</a><br><br/>
        <img :src="amazingImage" v-bind:alt="altText" :width="imageWidth" :height="imageHeight">
    </template>

</code>

<h3>Notes:</h3>

Write HTML is done inside the ```<template>...</template> ```tag.<br>
Write CSS is done inside the ```<style>...</style>``` tag.<br>
Write JS is done inside the``` <script>...</script>``` tag.<br>
Structure of component should be in js->html->css.
<h3>Standard Practices</h3>
Component name should be multiname.

Example: "HelloWorld.vue"


<h3>Command to do new Project Setup</h3>

<i>npm create vue@latest</i> </br>
<i>project-name: vue-course (exmaple name)</i></br>
<i>cd vue-course</i></br>
<i>npm install</i></br>
<i>npm run format</i></br>
<i>npm run dev</i></br>

### Component:
 Building blocks of Single Page Applications.

### Interpolation {{ }}:
Dynamically Binding Data to the content of an HTML element.

### Attribute Binding & Dynamic Attribute Binding  :attr or v-bind:attr:
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

### Vue Style: 

Global Style: ```<style>...</style>```

Local Style: ```<style scoped>...</style>```

Module Style: ```<style module>...<style>```
Example:
```
<template>
<h1 v-bind:class="$style['m-class']"> This is module example.</h1>

<h1 :class="$style.anotherClass"> This is another module example.</h1>
</template>

<style module>
/*Kebab style */
.m-class {
    background: firebrick;
    color: white;
}

/*for camel case style*/
.anotherClass {
    background: green;
    color: white;
}
</style>
```

### Events:
Two ways of using events:<br>
- ```v-on:click="count++"<br>```
- ```@:click="count++"```

Example:
```
<script setup>
import {ref} from 'vue';

let count = ref(0)
console.log('Count: ', count);

</script>

<template>
  <h1>Count: {{count}}</h1>
  <button v-on:click="count++">Increement</button>
  <button @:click="count--">Decreement</button>
</template>

```

### Reactivity:

Reactivity means that the framework can automatically update (UI) when the information behind it changes. It's a core concept that allow you to create dynamic and responsive applications without manually manipulating the DOM.

#### Reactive State:
- reactive()
    - The reactive function is used to create a reactive objects. A reactive object is an object where changes to its properties are automatically detected, triggering updates in the user interface. It is a way to make an object "reactive" in Vue.js.

    - Cannot Store primitive data types.
```
<script setup>
    import { reactive } from 'vue';

    let initialState = reactive({val: {count: 0}, user: ["Super", "Man"]})
    let changeUser = ()=> {
        initialState.user[0] = "Wondar",
        initialState.user[1] = "Women"
    }
</script>

<template>
    <h1> Current Count: {{initialState.val.count}}</h1>
    <h1>Users:  {{initialState.user}}</h1>
    <button @:click="initialState.val.count+=10">Add 10</button>
    <button @:click="initialState.val.count-=10">Substract 10</button>
    <button @:click="changeUser"> Change User </button>
    <button @:click="initialState.user.push('Super Man')">Add User</button>
</template>

```
- ref()
    - ref() is used to create a reactive reference to a value. Unlike the reactive function, which is used for creating reactive objects, ref is specifically designed for creating reactive single values.

    -  You can store any value you want.
```
<script setup>
    import { ref } from 'vue';
    // using ref for primitive value.
    let username = ref('');
    // using ref for arrays.
    let userList = ref(['Michel', 'Jordan', 'Super', 'Man'])
    // using ref for objects.
    let userInfo = ref({
        name: 'Salman Khan',
        profession: 'actor',
        age: 50,
        isMarried: false
    })
</script>

<template>
    <h1>Username : {{username}}</h1>
    <button @:click="username='Jordan'"> Add Username</button>
    <h1>UserList: {{userList}}</h1>
    <button @:click="userList.push('Batman')">Add User</button>
    <h1>Name: {{userInfo.name}}</h1>
    <h1>Age: {{userInfo.age}}</h1>
    <h1>IsMarries: {{userInfo.isMarried}}</h1>
    <h1>Profession: {{userInfo.profession}}</h1>
    <button @:click="userInfo.name='Amitab Bachan'">Change name</button>
</template>
```

#### Reactive System:
<i>ref in Vue 3 returns an object with a value property to enable Vue's reactivity system to track changes and update the DOM efficiently.</i>

#### Accessing ref Values:
<i>Use .value to read or write the value of a ref object. This ensures you are accessing the actual data.</i>

#### Direct Mutation with Increment/Decrement:
<i>Using count++ or count-- works because of JavaScript's ability to coerce objects during arithmetic operations. However, it's not the recommended approach.</i>

#### Best Practices:
<i>Always use .value for clarity, consistency, and alignment with Vue's documentation. This helps prevent confusion and makes your code more maintainable.</i>

### Computed Properties
A computed property is a special kind of variable that automatically updates itself whenever the data it depends on changes.

It's like a little worker that watches certain data, performs some work on it, and always give you most up-to-date result.
```
<script setup>
    import { ref, computed } from 'vue';
    let count = ref(0);
    let square = computed(()=>{return count.value**2;})
</script>

<template>
    <h1>Count : {{count}}</h1>
    <h1>Square: {{square}}</h1>
    <button @:click="count++">Increment</button>
</template>
```

### Conditional Rendering
Conditional rendering is refers to the ability to conditionally display or hide elements in the user interface based on certain condition or expressions.

-   v-if (condition)
-   v-else-if (condition)
-   v-else

```
<script setup>
    let isAuthorized = false
    let userInfo = {
        name: "Super Man",
        profession: "Super Hero",
        age: "50",
        address: "DC Universe"
    }
</script>

<template>
    <h1>User Info:</h1>
    <h1>Name: {{userInfo.name}}</h1>
    <h1>Profession: {{userInfo.profession}}</h1>
    <div v-if="isAuthorized">
        <h1>Age: {{userInfo.age}}</h1>
        <h1>Address: {{userInfo.address}}</h1>
    </div>
    <div v-else> 
        <h1>Do Login to see complete info.</h1>
    </div>
</template>
```
#### v-show
v-show directive is used for conditional rendering. It toggles the visibility of an element based on the truthiness of the provided expression. Unlike v-if, which completely adds or removes the element from the DOM, v-show toggles the CSS display property of the element to control its visibility while keeping it in the DOM.

```
<script setup>
    import { ref } from 'vue';
    let isVisible = ref(true);
</script>

<template>
    <h1>User Profile:</h1>
    <h2 v-show="isVisible">Name: Kaushal Agarwal</h2>
    <h2 v-show="isVisible">Age: 27</h2>
    <button @:click="isVisible = !isVisible">Hide Details</button>
</template>
```
#### Note: 
- v-show only toggle the visibility.
- Other conditional rendering remove it from DOM.
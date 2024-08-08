
## Notes:

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

## Component:
 Building blocks of Single Page Applications.

## Interpolation {{ }}:
Dynamically Binding Data to the content of an HTML element.

## Attribute Binding & Dynamic Attribute Binding  :attr or v-bind:attr:
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

## Vue Style: 

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

## Events:
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

## Reactivity:

Reactivity means that the framework can automatically update (UI) when the information behind it changes. It's a core concept that allow you to create dynamic and responsive applications without manually manipulating the DOM.

### Reactive State:
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

### Reactive System:
<i>ref in Vue 3 returns an object with a value property to enable Vue's reactivity system to track changes and update the DOM efficiently.</i>

### Accessing ref Values:
<i>Use .value to read or write the value of a ref object. This ensures you are accessing the actual data.</i>

### Direct Mutation with Increment/Decrement:
<i>Using count++ or count-- works because of JavaScript's ability to coerce objects during arithmetic operations. However, it's not the recommended approach.</i>

### Best Practices:
<i>Always use .value for clarity, consistency, and alignment with Vue's documentation. This helps prevent confusion and makes your code more maintainable.</i>

## Computed Properties
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

## Conditional Rendering
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
### v-show
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
### Note: 
- v-show only toggle the visibility.
- Other conditional rendering remove it from DOM.


### v-for
The v-for directive is used to iterate over an array or an object an render a template for each item in the collection.

```
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
```

### Efficient DOM Updates
Why :key?

• When Vue renders a list of elements, it uses a virtual DOM to determine the most efficient way to update the actual DOM. The key helps Vue identify which elements have changed, been added, or been removed.

• Without keys, Vue may need to recreate the entire DOM structure for each update, which can be less efficient.

### Avoiding Common Pitfalls

• Using key can help avoid common pitfalls, such as duplicate key warnings in the console or incorrect rendering when items are rearranged in the list.

• Vue relies on keys to track the identity of elements, and using unique keys for each item ensures that Vue can accurately update the DOM based on changes in the list.

## v-model
v-model is a directive that provides two-way data binding on an input, textarea, or select element. It creates a connection between the data in your component and the input field, allowing changes in one to automatically update the other and vice versa.

### Two Way Binding?
Two-way binding means that changes in your code automatically update what you see on the screen, and vice versa. It's like a live connection between your data and the user interface, making it easy to keep them in sync without writing a lot of extra code.

```
<script setup>
    import { ref } from 'vue';
    let formData = ref({
        username: '',
        email: '',
        password:''
    })
</script>

<template>
    <form @submit.prevent>
        <input type="text" placeholder="Please enter your username." v-model="formData.username"><br/><br/>
        <input type="email" placeholder="Please enter your email." v-model="formData.email"><br/><br/>
        <input type="password" placeholder="Please enter your password." v-model="formData.password"><br/><br/>
        <button type="submit">Submit</button>
    </form>
    <h1>{{formData.username}}</h1>
    <h1>{{formData.email}}</h1>
    <h1>{{formData.password}}</h1>
</template>
```

## Props

"props" (short for properties) are a way to pass data from a parent component to a child component Props allow you to communicate between components by allowing the parent component to pass data down to its child components. This is useful for creating reusable and modular components.

Props are readonly. There value cann't be change i.e. immutable.

### Static Props Example
```
<script setup>
    let props = defineProps(['name'])
</script>

<template>
    <h2>Name: {{props.name}}</h2>
</template>
```

### Dynamic Porps Example
```
<script setup>
    let props = defineProps(['counter'])
    // Props are "immutable" that means there value cannot be changed
    // They are just readonly.
    // props.counter=10; //It does not work it will give a warning at console.
</script>

<template>
    <h2>Counter: {{counter}}</h2>
</template>
```

### Props Validation Example
```
<script setup>
    let props = defineProps({
        fullname: String,
        age: Number
    })
</script>

<template>
    <h2>Fullname: {{props.fullname}}</h2>
    <h2>Age: {{props.age}}</h2>
</template>
```

### Complex Props Validation Example
```
<script setup>
    defineProps({
        fullname:{
            type:String,
            required:true
        },
        age:{
            type:Number,
            required:false
        }
    })
</script>

<template>
    <h2>Fullname: {{fullname}}</h2>
    <h2>Age: {{age}}</h2>
</template>
```

### Complex Object Props Example
```
<script setup>
    defineProps({
        book:Object,
        petNames:Array
    })
</script>

<template>
    <h2>Book Details:</h2>
    <li v-for="(c, i) in book" :key="i">{{c}}</li>
    <h2>Pet Names:</h2>
    <li v-for="(c,i) in petNames" :key="i">{{c}}</li>
</template>
```

### Custom Validation Props Example
```
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
```


## Component Event
Component events are a way for child components to communicate with their parent components. They allow child components to emit events (custom events) that can be listened to and handled by their parent components.

### Child Component Emits an Event
Inside a child component, you can use the $emit method to trigger a custom event. This event can carry data that you want to send to the parent.

### Parent Component Listens to the Event

In the parent component's template, you can use the v-on directive (or the shorthand @) to listen for the custom event emitted by the child.

<i>App.vue (Parent Component)</i>
```
<script setup>
  import FormComponent from './components/FormComponent.vue';
  const formHandler = (userInfo)=>{
    console.log(userInfo);
  }
</script>

<template>
  <FormComponent @getUserInfo="formHandler"/>
</template>
```

<i>FormComponent.vue (Child Component)</i>
```
<script setup>
    import { ref } from 'vue'; 
    let userInfo = ref({
        username:"",
        email:"",
        password:""
    })
</script>

<template>
    <form @submit.prevent="$emit('getUserInfo',userInfo)" >
        <input type="text" placeholder="username" v-model="userInfo.username"> <br>
        <input type="email" placeholder="email" v-model="userInfo.email"><br>
        <input type="password" placeholder="password" v-model="userInfo.password">
        <button @click="submit">Submit</button>
    </form>
</template>
```

## Slot
A slot is like a space in a component where you can put different things. It allow you to create reusable components that can accept different content while maintaining a consistent structure.

App.vue
```
<script setup>
  import SlotComponent from './components/SlotComponent.vue';
</script>

<template>
  <SlotComponent>
    <h1>Content 1</h1>
    <h2>Content 2</h2>
  </SlotComponent>
</template>
```

SlotComponent.vue
```
<script setup></script>
<template>
    <slot></slot>
</template>
```
### Fallback / Default Content
Fallback content in slots refers to the default content that is displayed when no content is provided for a particular slot. It's a way to ensure that a component still has meaningful content, even if the parent component does not pass any content to a specific slot.

App.vue
```
<script setup>
  import FallbackComponent from './components/FallbackComponent.vue';
</script>

<template>
  <FallbackComponent>

  </FallbackComponent>
  <hr>
  <FallbackComponent>
    Fallback Content does not work.
  </FallbackComponent>
</template>
```

FallbackComponent.vue
```
<script setup></script>

<template>
    <slot> This is fallback / default content</slot>    
</template>
```

### Named Slots
A named slot is a way to assign a specific name to a slot in a component. Unlike the default slot, which is unnamed and used when no explicit name is provided. named slots allow you to have multiple slots in a component and specify where the content should be inserted based on the slot's
name.

App.vue
```
<script setup>
  import NamedSlot from './components/NamedSlot.vue';
</script>

<template>
  <h1>NamedSlot Example.</h1>
  <NamedSlot>
      <template v-slot:one>
        <h2>This content go to slot "one".</h2>
      </template>
      <template #two>
        <h2>This content go to slot "two".</h2>
      </template>
  </NamedSlot>
</template>
```
NamedSlot.vue
```
<script setup></script>
<template>
    <slot name="one"></slot>
    <slot name="two"></slot>
</template>
```

### Default Slot
A default slot captures all the content that does not have a designated name and renders it at the location where the default <slot> tag is placed within the child component.

App.vue
```
<script setup>
  import DefaultSlot from './components/DefaultSlot.vue';
</script>

<template>
  <DefaultSlot>
    <template #example>
      <br>
      This is example slot.
    </template>
    <template #default>
      All the content which is not in named slot goes into default slot.
      </template>
  </DefaultSlot>
</template>
```
DefaultSlot.vue
```
<script setup>
</script>
<template>
    <slot></slot>
    <slot name="example"></slot>
</template>
```

## Provide & Iniect
The provide and inject options are used for providing and injecting properties or data down the component hierarchy.
They enable a form of dependency injection, allowing a parent component to provide data or methods that child components can then inject and use.

### Provide
Provide is an option in a parent component that allows it to share data or methods with its child components. It makes properties or methods available for injection into child components.

### Inject
Inject is an option in a child component that specifies which properties or methods it wants to receive from its parent component. It allows a component to inject and use
provided data or methods.

App.vue
```
<script setup>
  import {provide} from 'vue';
  import SchoolComponent from './components/SchoolComponent.vue';
  provide('studentName', 'Kaushal Agarwal');
  provide('studentEmail', 'Kaushal@gmail.com');
  provide('studentRollNumber', 11);
</script>

<template>
  <SchoolComponent/>
</template>
```

SchoolComponent.vue
```
<script setup>
    import StudentComponent from './StudentComponent.vue';
</script>

<template>
    <StudentComponent/>
</template>
```

StudentComponent.vue
```
<script setup>
    import {inject} from 'vue';
    const studentName = inject('studentName');
    const studentEmail = inject('studentEmail');
    const studentRollNumber = inject('studentRollNumber'); 
</script>

<template>
    <h1>Name: {{ studentName }}</h1>
    <h1>Email: {{ studentEmail }}</h1>
    <h1>Roll Number: {{ studentRollNumber }}</h1>
</template>
```

## Lifecycle Hooks
Lifecycle hooks are special methods provided by Vue.js that allow you to execute code at different stages of a component's lifecycle. These hooks provide developers with the ability to perform actions or respond to events at specific points during the creation, updating, and destruction of a Vue component.

### Mount 

Mounting means when a component is being created and inserted into the DOM.

### Unmount
Unmounting means when a component is being removed from the DOM.

### onBeforeMount()
-   Registers a hook to be called right before the component is to be mounted.
-   When this hook is called, the component has finished setting up its reactive state, but no DOM nodes have been created yet.
-   It is about to execute its DOM render effect for the first time.

### onMounted ()
onMounted is used for executing logic or actions after a component has been mounted to the DOM. This hook is particularly useful for tasks that should occur once the
component is ready to interact with the user, such as fetching data, setting up event listeners, or performing initial calculations.

### onBeforeUpdate()
Registers a hook to be called right before the component is about to update its DOM tree due to a reactive state change.
This hook can be used to access the DOM state before Vue updates the DOM. It is also safe to modify component state inside this hook.

### onUpdated()
Registers a callback to be called after the component has updated its DOM tree due to a reactive state change.
This hook is called after any DOM update of the component, which can be caused by different state changes, because multiple state changes can be batched into a single render cycle for performance reasons.

### onBeforeUnmount ()
Registers a hook to be called right before a component instance is to be unmounted.
When this hook is called, the component instance is still fully functional.

### onUnmounted ()
Registers a callback to be called after the component has been unmounted.
Use this hook to clean up manually created side effects such as timers, DOM event listeners or server connections.

App.vue
```
<script setup>
    import {ref} from 'vue';
    import LifeCycleComponent from './components/LifeCycleComponent.vue';
    let showHide = ref(false)
</script>


<template>
    <LifeCycleComponent v-if="showHide"/>
    <button @click="showHide=!showHide">Show/Hide</button>
</template>
```

LifeCycleComponent.vue
```
<script setup>
    import {
        ref,
        onBeforeMount,
        onMounted,
        onBeforeUpdate,
        onUpdated,
        onBeforeUnmount,
        onUnmounted
    } from 'vue';

    onBeforeMount(()=>{
        console.log('Component is about to be mounted');
    })

    onMounted(()=>{
        console.log('Component is has been mounted');
    })

    onBeforeUpdate(()=>{
        console.log('Component is about to update');
    })

    onUpdated(()=>{
        console.log('Component has been Updated.');
    })

    onBeforeUnmount(()=>{
        console.log('Component is about to unmounted');
    })

    onUnmounted(()=>{
        console.log('Component has been unmounted');
    })

    const message = ref('Hello World');
    const updateMessage = ()=>{
        message.value = 'Updated Value!';
    }
</script>

<template>
    <p>{{message}}</p>
    <button @:click="updateMessage">Update Message</button>
</template>
```

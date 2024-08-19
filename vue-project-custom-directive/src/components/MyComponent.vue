<script setup>
    const vFormatDiv1 = {
        mounted:(el, binding) =>{
            el.style.fontSize = `${binding.value}rem`
            el.style.border = `${binding.value}rem solid teal`
        }
    }

    const vFormatDiv2 = {
        mounted:(el, binding)=>{
            console.log('Inside div2');
            console.log('Binding arg: ', binding.arg);
            console.log('Binding value: ', binding.value);
            el.style.fontSize = `${binding.value}rem`
            switch(binding.arg){
                case 'orange': 
                    el.style.color = 'orange'
                    break
                case 'pink': 
                    el.style.color = 'pink'
                    break
                case 'purple': 
                    el.style.color = 'purple'
                    break
                case 'teal': 
                    el.style.color = 'teal'
                    break
                default: 
                    el.style.color = 'black'
                    break
            }
        }
    }

    const vFormatDiv3 = (el) => el.style.fontSize='5rem';
</script>

<template>
    <div v-format-div1="5">Using simple custom directives</div>
    <div v-format-div2:orange="5">Using simple custom directives with binding arg</div>
    <div v-format-div3>Shorthand of using custom directive.</div>
</template>

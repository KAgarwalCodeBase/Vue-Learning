<script setup>
  import SlotComponent from './components/SlotComponent.vue';
  import FallbackComponent from './components/FallbackComponent.vue';
  import NamedSlot from './components/NamedSlot.vue';
  import DefaultSlot from './components/DefaultSlot.vue';
</script>


<template>
  <h1>Slot Example.</h1>
  <SlotComponent>
    <h1>Content 1</h1>
    <h2>Content 2</h2>
  </SlotComponent>
  <hr>
  <h1>Fallback Slot Example.</h1>
  <h2>Component 1</h2>

  <FallbackComponent>

  </FallbackComponent>
  <br>
  <h2>Component 2</h2>
  <FallbackComponent>
    Fallback Content does not work.
  </FallbackComponent>
  <hr>
  <h1>NamedSlot Example.</h1>
  <NamedSlot>
    <template v-slot:one>
        <h2>This content go to slot "one".</h2>
      </template>
      <template #two>
        <h2>This content go to slot "two".</h2>
      </template>  
    </NamedSlot>

  <hr>
  <h1>DefaultSlot Example.</h1>
  <DefaultSlot>
    <template #example>
      <br>
      This is example slot.
    </template>
    <template #default>
        Default slot always come first.
      </template>
  </DefaultSlot>
</template>
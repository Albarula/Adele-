<template>
  
  <CompHeader></CompHeader>
  <HelloWorld></HelloWorld>
  <CompFooter></CompFooter>
  
</template>

<script>

import CompHeader from './components/CompHeader.vue'
import CompFooter from './components/CompFooter.vue'
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    CompHeader,
    CompFooter,
    HelloWorld
  }
}
</script>

<template>
  
  <CompHeader></CompHeader>
  <CompImgfooter></CompImgfooter>
  <CompFooter></CompFooter>
  <p>Hello Eugenia1</p>
</template>

<script>

import CompHeader from './components/CompHeader.vue'
import CompFooter from './components/CompFooter.vue'
import CompImgfooter from './components/CompImgfooter.vue';

export default {
  name: 'App',
  components: {
    CompHeader,
    CompFooter,
    CompImgfooter
  }
}
</script>

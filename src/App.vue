<template>
  
  <CompHeader></CompHeader>
  <CompImgfooter></CompImgfooter>
  <CompFooter></CompFooter>
  
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

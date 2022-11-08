<template>
  <CompHeader></CompHeader>
  <playList></playList>
  <AlbumsComps></AlbumsComps>
  <AboutAdele></AboutAdele>
  <CompImgfooter></CompImgfooter>
  <CompFooter></CompFooter>
</template>

<script>

import CompHeader from './components/CompHeader.vue'
import CompFooter from './components/CompFooter.vue'
import CompImgfooter from './components/CompImgfooter.vue';
import playList from "./components/playlist/playlist.vue";
import AboutAdele from "./components/AboutView.vue";
import AlbumsComps from "./components/albums.vue";

export default {
  name: "App",
  components: {
    CompHeader,
    CompFooter,
    playList,
    AboutAdele,
    AlbumsComps,
    CompImgfooter
  }
}

</script>

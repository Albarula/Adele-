<template>
  <CompHeader></CompHeader>
  <playList></playList>
  <AlbumsComps></AlbumsComps>
  <AboutAdele></AboutAdele>
  <HelloWorld></HelloWorld>
  <CompFooter></CompFooter>
</template>

<script>
import CompHeader from "./components/CompHeader.vue";
import CompFooter from "./components/CompFooter.vue";
import HelloWorld from "./components/HelloWorld.vue";
import playList from "./components/playlist/playlist.vue";
import AboutAdele from "./components/AboutView.vue";
import AlbumsComps from "./components/albums.vue";

export default {
  name: "App",
  components: {
    CompHeader,
    CompFooter,
    HelloWorld,
    playList,
    AboutAdele,
    AlbumsComps,
  },
};
</script>

<template>
  <div id="playlist" class="bg-zinc-900 p-0">
    <div class="m-8 p-8">
      <h2 class="font-serif text-2xl text-white">Escucha nuestro Top 5</h2>
      <SongList> </SongList>
    </div>
  </div>
</template>

<script>
import SongList from "./SongList.vue";

export default {
  name: "playList",
  components: {
    SongList,
  },
};
</script>

<style></style>

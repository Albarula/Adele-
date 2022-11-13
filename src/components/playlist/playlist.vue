<template>
  <div id="playlist" class="bg-zinc-900 p-2 md:p-5 lf:p-6">
    <div class="m-2 md:m-6 lg:m-8 p-4 md:p-8 lg:p-8">
      <h2 class="font-serif text-3xl md:text-4xl lg:text-5xl text-white pb-4">
        Escucha nuestro Top 5
      </h2>
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

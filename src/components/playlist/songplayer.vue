<template>
  <div class="text-white">
    <div>
      <button @click="showList()" class="underline">ShowList</button>
    </div>
    <!--    song information  -->
    <div id="info-display" class="flex m-8">
      <img
        id="imagen-album"
        class="object-cover h-48 rounded"
        v-bind:src="song.src"
      />
      <div id="info-songs">
        <h3 class="text-5xl font-serif text-left pl-6 px-5">
          {{ song.artistName }}
        </h3>
        <p class="pl-6">{{ song.name }}</p>
        <p class="pl-6">{{ song.year }}</p>

        <!-- music display  -->
        <div id="music-display" class="flex items-center p-5">
          <div v-on:click="previous()" class="justify-center p-5">
            <button><img class="h-3" src="./icons/previous.png" /></button>
          </div>
          <div class="flex justify-center p-5">
            <button v-on:click.prevent="playsong()">
             <!--  <audio
                controls
                v-bind:src="song.music"
                autoplay
                ref="audioPlayer"
              ></audio> -->
            </button>
          </div>
          <div class="flex items-center justify-center p-5">
            <button v-on:click="next()">
              <img class="h-3" src="./icons/next.png" />
            </button>
          </div>
        </div>
      </div>
    </div>
    <!-- showme the list  -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPlaying: true,
    };
  },
  name: "songPlayer",
  props: {
    song: {
      id: Number,
      name: String,
      artistName: String,
      albumName: String,
      year: Number,
      src: String,
      music: String,
    },
  },
  emits: ["showlist", "next", "previous"],
  methods: {
    showList() {
      this.$emit("showlist");
    },
    playsong() {
      if (this.isPlaying) {
        this.$refs.audioPlayer.pause();
      } else {
        this.$refs.audioPlayer.play();
      }
      this.isPlaying = !this.isPlaying;
    },
    next() {
      this.$emit("next");
    },
    previous() {
      this.$emit("previous");
    },
  },
};
</script>

<!-- <style scoped>
audio {
  filter: sepia(20%) saturate(70%) grayscale(1) contrast(99%) invert(12%);
  width: 600px;
}
</style> -->

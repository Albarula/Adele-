<template>
  <div class="text-white">
    <div>
      <button @click="showList()" class="underline">ShowList</button>
    </div>
    <!--    song information  -->
    <div id="info-display" class="grid grid-flow-col auto-cols-max m-8">
      <img
        id="imagen-album"
        class="object-cover h-48 rounded"
        v-bind:src="song.src"
      />
      <div>
        <div id="info-songs">
          <h3 class="text-5xl font-serif text-left pl-6 px-5">
            {{ song.artistName }}
          </h3>
          <p class="pl-6">{{ song.name }}</p>
          <p class="pl-6">{{ song.year }}</p>
          <!-- music display  -->
          <div class="flex items-center p-5">
            <div v-on:click="previous()" class="p-5">
              <button><img class="h-3" src="./icons/previous.png" /></button>
            </div>

            <div class="md:flex flex-row p-5">
              <button v-on:click.prevent="playsong()" class="w-3/4 md:w-auto">
                <audio
                  controls
                  v-bind:src="song.music"
                  ref="audioPlayer"
                ></audio>
              </button>
            </div>
            <div class="flex items-center justify-center p-5">
              <button v-on:click="next()">
                <img class="h-3" src="./icons/next.png" />
              </button>
            </div>
          </div>
          <div class="md:hidden sm:flex">
            <div v-on:click="previous()" class="p-5">
              <button><img class="h-3" src="./icons/previous.png" /></button>
            </div>
            <button v-on:click.prevent="playsong()" class="w-3/4 md:w-auto">
              <audio controls v-bind:src="song.music" ref="audioPlayer"></audio>
            </button>
            <div class="flex items-center justify-center p-5">
              <button v-on:click="next()">
                <img class="h-3" src="./icons/next.png" />
              </button>
            </div>
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

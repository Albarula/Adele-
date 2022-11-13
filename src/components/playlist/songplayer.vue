<template>
  <div class="text-white m-0 md:m-2 lg:m-4">
    <div class="mb-8">
      <button @click="showList()">🧾 <u> ShowList</u></button>
    </div>
    <!--    song information  -->
    <div id="info-display" class="grid grid-flow-col m-0 md:m-2 lg:m-4">
      <div class="hidden md:flex flex-row items-center justify-between">
        <img
          id="imagen-album"
          class="object-cover h-48 lg:h-52 rounded"
          v-bind:src="song.src"
        />
      </div>
      <div class="col-span-4">
        <div id="info-songs" class="pt-0 mlg:pt-8">
          <h3 class="text-5xl font-serif text-left pl-6 pt-4">
            {{ song.artistName }}
          </h3>
          <p class="pl-6">{{ song.name }}</p>
          <p class="pl-6">{{ song.year }}</p>
          <!-- music display  -->
          <div class="flex items-center p-2 md:p-5 lg:p-6">
            <div v-on:click="previous()" class="p-5">
              <button><img class="h-3" src="./icons/previous.png" /></button>
            </div>


            <div class="md:flex flex-row p-2 md:p-5 lg:p-">
              <button v-on:click.prevent="playsong()" class="max-w-md">
                <audio
                  controls
                  v-bind:src="song.music"
                  ref="audioPlayer"
                ></audio>
              </button>
            </div>
            <div class="flex items-center justify-center p-2 md:p-5 lg:p-">
              <button v-on:click="next()">
                <img class="h-3" src="./icons/next.png" />
              </button>
            </div>
          </div>
          <!--    <div class="flex items-center justify-center p-5">
            <button v-on:click="next()">
              <img class="h-3" src="./icons/next.png" />
            </button>
          </div> -->
        </div>
      </div>
    </div>
  </div>
  <!-- showme the list  -->
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

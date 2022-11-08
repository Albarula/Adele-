<template>
  <div class="text-white">
    <!--    song information  -->
    <div id="info-display">
      <img
        id="imagen-album"
        class="object-cover rounded ml-5"
        v-bind:src="song.src"
      />
      <div id="info-songs">
        <h3 class="text-4xl font-serif text-left">{{ song.artistName }}</h3>
        <p>{{ song.name }}</p>
        <p>{{ song.year }}</p>
      </div>
    </div>
    <!-- music display  -->
    <div id="music-display" class="grid grid-cols-3">
      <div v-on:click="previous()" class="flex items-cente justify-center">
        <button><img class="iconsP" src="./icons/previous.png" /></button>
      </div>
      <div class="flex items-cente justify-center">
        <button v-on:click.prevent="playsong()">
          <audio
            controls
            v-bind:src="song.music"
            autoplay
            ref="audioPlayer"
          ></audio>
        </button>
      </div>
      <div class="flex items-cente justify-center">
        <button v-on:click="next()">
          <img class="iconsN" src="./icons/next.png" />
        </button>
      </div>
    </div>
    <!-- showme the list  -->
    <div>
      <button @click="showList()">ShowList</button>
    </div>
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

<style scoped>
button {
  color: white;
}
h3 {
  font-size: 27px;
}
#imagen-album {
  width: 100%;
  border-radius: 10px;
  margin-top: 20px;
}
#music-display {
  display: grid;
  grid-template-columns: repeat(3, 4fr);
  grid-gap: 10px;
  grid-auto-rows: minmax(100px, auto);
  margin-block: auto;
}
#info-display {
  display: grid;
  grid-template-columns: repeat(6, 2fr);
  grid-gap: 10px;
  grid-auto-rows: minmax(100px, auto);
  align-items: center;
  margin: 20px 0px 10px 50px;
}
#info-songs {
  grid-column: 2 /6;
  margin: 110px 50px 10px 50px;
  grid-auto-rows: minmax(100px, auto);
}
.iconsP {
  width: 7%;
  margin-left: 220px;
  align-items: center;
}
.iconsN {
  width: 7%;
  margin-right: 220px;
  align-items: center;
}
audio {
  filter: sepia(20%) saturate(70%) grayscale(1) contrast(99%) invert(12%);
  width: 600px;
}
</style>

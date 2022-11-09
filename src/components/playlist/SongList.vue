<template>
  <div v-if="!playVisibity" class="flex justify-center m-8 gap-4">
    <div
      id="song"
      v-for="(song, songIndex) in list"
      v-bind:key="song.id"
      v-on:click="playSong(songIndex)"
      class="justify-between mb-4 cursor-pointer"
    >
      <div>
        <img
          id="songImage"
          class="object-cover h-48 rounded-lg"
          v-bind:src="song.src"
        />
        <div class="text-white">
          <h3 class="text-xl font-serif">{{ song.name }}</h3>
          <p>
            <b>{{ song.albumName }} </b> -({{ song.year }})
          </p>
        </div>
      </div>
    </div>
  </div>
  <div v-if="playVisibity">
    <songplayer
      v-bind:song="list[currentSong]"
      @showlist="playVisibity = !playVisibity"
      @next="playNext"
      @previous="playPrevious"
    ></songplayer>
  </div>
</template>

<script>
import songplayer from "./songplayer.vue";

export default {
  data() {
    return {
      playVisibity: true,
      currentSong: 0,
      list: [
        {
          id: 1,
          name: "Oh my God",
          artistName: "Adele",
          albumName: "30",
          year: 2021,
          src: `https://m.media-amazon.com/images/I/71-llhQmneL._SL1500_.jpg`,
          music: require("./songs/AdeleOhMyGod.mp3"),
        },
        {
          id: 2,
          name: "Easy On Me",
          artistName: "Adele",
          albumName: "30",
          year: 2021,
          src: `https://m.media-amazon.com/images/I/71-llhQmneL._SL1500_.jpg`,
          music: require("./songs/AdeleEasyOnMe.mp3"),
        },
        {
          id: 3,
          name: "Someone Like you",
          artistName: "Adele",
          albumName: "21",
          year: 2011,
          src: `https://m.media-amazon.com/images/I/61lMwNQGYbL._SL1200_.jpg`,
          music: require("./songs/AdeleSomeoneLikeYou.mp3"),
        },
        {
          id: 4,
          name: "Hello",
          artistName: "Adele",
          albumName: "25",
          year: 2013,
          src: `https://m.media-amazon.com/images/I/81q0mwIoc0L._SL1500_.jpg`,
          music: require("./songs/AdeleHello.mp3"),
        },
        {
          id: 5,
          name: "Set Fire To The Rain",
          artistName: "Adele",
          albumName: "21",
          year: 2011,
          src: `https://m.media-amazon.com/images/I/61lMwNQGYbL._SL1200_.jpg`,
          music: require("./songs/AdeleSetFireToTheRain.mp3"),
        },
      ],
    };
  },
  methods: {
    playSong(index) {
      this.currentSong = index;
      this.playVisibity = true;
    },
    playNext() {
      if (this.currentSong < this.list.length - 1) {
        this.currentSong += 1;
      } else {
        this.currentSong = 0;
      }
    },
    playPrevious() {
      if (this.currentSong != 0) {
        this.currentSong -= 1;
      } else {
        this.currentSongIndex = this.list.length - 1;
      }
    },
  },
  name: "SongList",
  components: {
    songplayer,
  },
};
</script>

<style>
img {
  height: 20%;
}
</style>

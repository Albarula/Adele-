<template>
  <h1 class="text-4xl font-serif text-center">ÁLBUMS</h1>
  <div v-for="album in albums" :key="album.id" class="mx-6">
    <div class="flex flex-row-5">
      <button v-on:click="showDetails()">
        <div>
          <div class="flex flex-col">
            <img v-bind:src="album.src" class="object-cover h-48 rounded-lg" />
            <h3 class="text-slate-900 text-2xl font-serif text-left">
              {{ album.albumName }}
            </h3>
            <p class="text-slate-800 text-left">{{ album.year }}</p>
          </div>
        </div>
      </button>
    </div>

    <div v-show="show" :key="id">
      <p class="text-slate-900">{{ album.description }}</p>
    </div>
  </div>
</template>

<script>
import database from "./albums/dataBaseAdele.js";

export default {
  name: "AlbumsComps",
  data() {
    return {
      albums: database,
      show: false,
      album: 0,
    };
  },
  methods: {
    showDetails(index) {
      this.album = index;
      this.show = !this.show;
    },
  },
};
</script>

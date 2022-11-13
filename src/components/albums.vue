<template>
  <div id="albumscomp" class="py-12">
    <h1 class="text-4xl font-serif text-center py-4">ÁLBUMS</h1>
    <div class="py-6">
      <div class="hidden lg:flex justify-center m-auto md:m-2 lg:m-4 gap-2">
        <div v-for="album in albums" :key="album.id" class="mx-6 mb-20">
          <div class="hidden md:flex justify-center m-auto">
            <button
              @click="showDetails(album.id)"
              class="bg-white rounded-lg p-2 hover:bg-gray-100 hover:drop-shadow-md"
            >
              <div>
                <div>
                  <img
                    v-bind:src="album.src"
                    class="object-cover h-22 md:h-36 lg:h-48 rounded"
                  />
                  <h3
                    class="text-slate-900 font-medium text-3xl font-serif text-left"
                  >
                    {{ album.albumName }}
                  </h3>
                  <p class="text-slate-800 text-left my-1">{{ album.year }}</p>
                </div>
              </div>
            </button>
          </div>
          <div class="">
            <div
              v-if="idAlbumToShow === album.id"
              :key="album.id"
              class="absolute w-3/4 left-1/2 -translate-x-1/2 bg-white m-2 p-5"
            >
              <p class="text-slate-900">{{ album.description }}</p>
            </div>
          </div>
        </div>
      </div>
      <div class="flex flex-col lg:hidden mx-2">
        <div v-for="album in albums" :key="album.id">
          <button @click="showDetails(album.id)" class="mx-4">
            <div>
              <div class="mx-28">
                <div>
                  <img
                    v-bind:src="album.src"
                    class="object-contain h-18 rounded"
                  />
                </div>
                <h3
                  class="text-slate-900 font-medium text-3xl font-serif text-left"
                >
                  {{ album.albumName }}
                </h3>
                <p class="text-slate-800 text-left my-1">{{ album.year }}</p>
              </div>
            </div>
          </button>
          <div class="m-2 pb-4">
            <div
              v-if="idAlbumToShow === album.id"
              :key="album.id"
              class="p-5 bg-slate-200 rounded"
            >
              <p class="text-slate-900">{{ album.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import database from "./albums/dataBaseAdele.js";

export default {
  name: "AlbumsComps",
  data() {
    let showVar = Object.assign(
      {},
      ...database.map((x) => ({ [x.id]: false }))
    );
    return {
      albums: database,
      show: showVar,
      idAlbumToShow: null,
    };
  },
  methods: {
    showDetails(index) {
      if (index === this.idAlbumToShow) {
        this.idAlbumToShow = null;
      } else {
        this.idAlbumToShow = index;
      }

      // this.show[index] = !this.show[index];
    },
  },
};
</script>

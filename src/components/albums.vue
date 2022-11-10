<template>
  <div id="albumscomp" class="py-12">
    <h1 class="text-4xl font-serif text-center py-4">ÁLBUMS</h1>
    <div class="py-6">
      <div class="flex justify-center m-8 gap-4">
        <div v-for="album in albums" :key="album.id" class="mx-6 mb-20">
          <div>
            <button @click="showDetails(album.id)" class="mb-2">
              <div>
                <div>
                  <img
                    v-bind:src="album.src"
                    class="object-cover h-48 rounded"
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
          <div>
            <div
              v-if="idAlbumToShow === album.id"
              :key="album.id"
              class="absolute fixed left-1/2 -translate-x-1/2 bg-white p-2"
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

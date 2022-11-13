<template>
    <div id="concertscomp" class="grid md:grid-cols-2 lg:grid-cols-3">
        <!-- Photo -->
        <div class="md:grid md:grid-cols-2 md:col-span-1 lg:grid-cols-3 lg:col-span-1 md:bg-yellow-200 lg:bg-gray-900">
            <img class="w-full md:col-span-3" src="../assets/adeleconc.png" alt="">
        </div>
        <!-- Conciertos -->
        <div class="md:grid-cols-2 md:col-span-1 lg:grid-cols-3 lg:col-span-2 text-center
                    md:bg-yellow-500 lg:bg-white">
            <h1 class="text-2xl md:text-3xl lg:text-4xl font-serif uppercase py-3 md:py-5 xl:py-10">Conciertos</h1>
            <button type="submit"
                    class="h-10 w-1/4 text-gray-900 bg-white border border-gray-300
                             focus:outline-none hover:bg-gray-100 focus:ring-4 focus:ring-gray-200 font-medium rounded-full text-sm px-5 py-2.5 mr-2 mb-2 2xl:my-10 dark:bg-gray-800 dark:text-white dark:border-gray-600 dark:hover:bg-gray-700 dark:hover:border-gray-600 dark:focus:ring-gray-700"
                    v-on:click="getShows(0)">find
            </button>
            <!-- Lista de Conciertos -->
            <div v-if="eventos"
                 class="w-10/12 lg:w-2/3 xl:w-1/2 ml-auto mr-auto">
                <!-- <h3 class="text-gray-800 text-lg ">encontramos <span class="text-yellow-600 font-semibold  ">{{ eventos.page.totalElements }}</span> eventos, <span>({{ totalPages() }} paginas x {{ elementsPerPage }} )</span>estamos a {{ currentPage+1 }}</h3>    -->
                <ul>                                          
                    <li v-for:="events in eventos._embedded.events" :key="events"        
                         class="text-left shadow-sm md:shadow-md my-2 hover:bg-slate-200"
                         @click="showAttraction">
                        {{events.name}} <br>
                        {{events.dates.start.localDate}} <br>
                        {{events._embedded.venues[0].name}} in 
                        {{events._embedded.venues[0].city.name}},
                        {{events._embedded.venues[0].country.countryCode}}
                    </li>
                </ul>

                <nav class="bg-slate-200 h-12 ml-auto mr-auto rounded-md">
                    <ul class="h-12 m-2 flex flex-row items-center justify-between">
                        <li v-on:click.prevent="prevClick()">
                            <a class="py-2 px-3 ml-0 bg-white hover:bg-slate-300 border rounded-l-md border-gray-300" href="#">
                                <i class="w-5 h-5 fa-sharp fa-solid fa-arrow-left text-lg text-slate-500"></i>
                                <!-- &larr; -->
                            </a>
                        </li>                        
                        <li v-on:click.prevent="nextClick()">
                            <a class="py-2 px-3 mr-0 bg-white hover:bg-slate-300 border rounded-r-md border-gray-300" href="#">
                                <i class="w-5 h-5 fa-sharp fa-solid fa-arrow-right text-lg text-slate-500"></i>
                                <!-- &rarr; -->
                            </a>
                        </li>
                    </ul>
                </nav>

                <div v-if="showAttractionModal">
                    <AttractionModal :header-name = "eventos._embedded.events[0].name" 
                                 :imageUrl = "eventos._embedded.events[0].images[0].url"
                                 @close="showAttraction" />
                </div>
            </div>
        </div>        
    </div>
    
</template>

<script>
import AttractionModal from './AttractionModalView.vue'
export default {
    name: "ConciertosView",
    components: { AttractionModal },
    data() {
        return {
            eventos: null,
            error:'',
            key: 'o5gbvSYDrZAEYhCXE11sLyK8G0t5e4Qs',
            showAttractionModal: false,
            elementsPerPage: 6,
            currentPage:0
        }
    },
    methods: {
        getShows(numPage) {
            this.currentPage = numPage;
          
            let url = `https://app.ticketmaster.com/discovery/v2/events.json?attractionId=K8vZ917Gku7&sort=date,asc&apikey=${this.key}&size=${this.elementsPerPage}&page=${this.currentPage}`;
            fetch(url)
                .then(response => response.json())
                .then(datos => this.eventos = datos)                
                //.then(datos => console.log(datos))
                .catch((e) => (this.error =e));
        },
        nextClick() {
            this.currentPage++;
            if (this.currentPage > (this.totalPages()-1)){
                this.currentPage = 0
            } 
            this.getShows(this.currentPage)
        },
        prevClick() {
            this.currentPage--;
            if (this.currentPage < 0) {
                this.currentPage = this.totalPages()-1
            } 
            this.getShows(this.currentPage)
        },
        showAttraction() {
            this.showAttractionModal = !this.showAttractionModal
        },
        totalPages() {
            return Math.ceil(this.eventos.page.totalElements / this.elementsPerPage)
        }
        
    }
}

</script>
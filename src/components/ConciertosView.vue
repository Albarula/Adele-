<template>
    <div class="grid grid-cols-3">
        <!-- Photo -->
        <div class="col-span-1">
            <img class="w-full" src="../assets/adeleconc.png" alt="">
        </div>
        <!-- Conciertos -->
        <div class="col-span-2 text-center bg-slate-50">
            <h1 class="text-4xl font-serif uppercase py-10">Conciertos</h1>
            <button type="submit"
                    class="h-10 w-1/4 border-2 border-gray-600 rounded-lg"
                    v-on:click="getShows()">find
            </button>
            <!-- Lista de Conciertos -->
            <div v-if="eventos">
                <h3 class="text-gray-800 text-lg ">encontramos <span class="text-yellow-600 font-semibold  ">{{ eventos.page.totalElements }} </span> eventos, <span>(in total {{ totalPages() }} pages )</span> </h3>
                
                <ul class="">
                    <!-- <li v-for:="events in eventos._embedded.events" :key="events" -->
                        <li v-for:="events in dataPerPage" :key="events"
                         class="md:w-1/2 lg:w-1/3 ml-2 mr-2 md:ml-auto md:mr-auto text-left shadow-sm md:shadow-md my-2 hover:bg-slate-200"
                         @click="showAttraction">
                        {{events.name}} <br>
                        {{events.dates.start.localDate}} <br>
                        {{events._embedded.venues[0].name}} in 
                        {{events._embedded.venues[0].city.name}},
                        {{events._embedded.venues[0].country.countryCode}}
                    </li>
                </ul>
                <nav class="panel-footer bg-purple-300 w-96 h-10 ml-auto mr-auto">
                    <ul class="m-8 items-center flex justify-between">
                        <li id="prev" class="previous"><a href="#">&larr;</a></li>
                        <li v-for:="page in totalPages()" v-on:click="getDataPage(page)" class="pageItem"><a href="#">{{ page }}</a></li>
                        <li id="next" class="next"><a href="#">&rarr;</a></li>
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
//import { response } from 'express';
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
            dataPerPage: []
        }
    },
    // mounted(){
    //     //this.getShows();
    //     this.getDataPage(1);
    // },
    methods: {
        getShows() {
            let url = `https://app.ticketmaster.com/discovery/v2/events.json?attractionId=K8vZ917Gku7&size=200&sort=date,asc&apikey=${this.key}`;
            fetch(url)
                .then(response => response.json())
                .then(datos => this.eventos = datos)
                //.then(datos => console.log(datos))
                .catch((e) => (this.error =e));
            console.log(this.getDataPage(1));
        },
        showAttraction() {
            this.showAttractionModal = !this.showAttractionModal
        },
        totalPages() {
            return Math.ceil(this.eventos.page.totalElements / this.elementsPerPage)
        },
        getDataPage(numPage) {
            this.dataPerPage = [];
            let ini = (numPage*this.elementsPerPage) - this.elementsPerPage;
            //let fin = 0;
            let fin = numPage*this.elementsPerPage;
            let tail = this.eventos.page.totalElements % this.elementsPerPage;
            if ((tail != 0) && (numPage === this.totalPages()))
             {
                fin = fin-this.elementsPerPage + tail
             }
           
             this.dataPerPage = this.eventos._embedded.events.slice(ini,fin);
        }
    }
}

</script>
<template>
    <div class="bg-slate-400 bg-opacity-50 w-full h-full top-0 sm:left-1/3 fixed">
        <div class="bg-white  max-w-xs lg:max-w-lg
             mt-28 md:mt-48 lg:mt-80
            ml-6 sm:ml-10 md:ml-40  xl:ml-80 p-5 border-slate-50 rounded"
             @click="closeModal">
            <!-- <h1>{{ headerName }}</h1>
            <img class="w-full" src="'imageUrl'" alt=""> <br>
            <p class="text-xl text-gray-900">Attraction content</p> -->
            <p class="">Aquí tiene que haber más información del evento. Por ahora no está echo. Estoy trabajando en ello... <br></p>
            <p class="mt-6">Para cerrar esta ventana, hacer un click en ella.</p>
        </div>
    </div>
</template>

<script>
    export default {
       props: ['headerName','imageUrl'],
       methods: {
        closeModal() {
           this.$emit('close') 
        }
       } 
    }
</script>


<template>
    <div class="bg-slate-400 bg-opacity-50  w-full h-full top-0 fixed">
        <div class="bg-white w-96 p-5 m-96 border-slate-50 rounded "
             @click="closeModal">
            <h1>{{ headerName }}</h1>
            <img class="w-full" src="'imageUrl'" alt=""> <br>
            <p class="text-xl text-gray-900">Attraction content</p>
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


<template>

    <div id="adelefooter" class="bg-[url('../assets/adelefooter.png')] sm:h-full lg:h-max bg-cover bg-no-repeat" src="../assets/adelefooter.png">


    <!-- <div class="md:col-span-4 pt-80 pb-16 ml-24 md:mb-0">
      <p class="text-black font-serif text-2xl">¡Sé el primero en enterarte de las últimas novedades!</p>
      <div class="pt-5 space-x-4">
        <input type="text" class="rounded p-2 w-80 text-sm border-2 border-slate-200 " placeholder="Email">
        <button class="bg-fuchsia-400 border-fuchsia-400 text-white px-3 py-2 rounded mt-2 text-sm">Unirme</button>
      </div>
    </div>
    </div> -->

    <!-- PRUEBA SALUDO BOTÓN -->

    <div class="md:col-span-4 pt-80 pb-16 ml-24 md:mb-0">
      <p class="text-black font-serif text-2xl">¡Sé el primero en enterarte de todas las novedades!</p>
      <div class="pt-5 space-x-3">
        <input type="text" class="rounded p-2 w-36 text-sm border-2 border-slate-200 " placeholder="Nombre">
        <input type="text" class="rounded p-2 w-64 text-sm border-2 border-slate-200 " placeholder="Email">
        <button v-on:click="unir" class="bg-fuchsia-400 border-fuchsia-400 text-white px-3 py-2 rounded mt-2 text-sm">Unirme</button>
      </div>
    </div>
    </div>

</template>

<script>
    export default {
        name:'HelloWorld'
    }

</script>
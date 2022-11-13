<template>
    <div id="adelefooter" class="bg-[url('../assets/adelefooter.png')] lg:h-max bg-cover bg-no-repeat" src="../assets/adelefooter.png">
      <div class="md:col-span-4 pt-80 pb-16 ml-24 md:mb-0 ">
        <p v-show="show" class="text-black font-serif font-semibold text-3xl pb-3"> ¡Felicidades {{nombre}}!</p>
        <p v-show="show" class="text-black font-serif text-xl"> Lo último de Adele te espera en tu correo :D</p>
        <p v-show="sentence" class="text-black font-serif text-2xl">¡Sé el primero en enterarte de todas las novedades!</p>
        <div class="pt-5 space-x-3">
          <input v-show="sentence" v-model="nombre" type="text" class="rounded p-2 w-32 text-sm border-1 border-slate-200 " placeholder="Nombre">
          <input v-show="sentence" type="text" class="rounded p-2 w-60 text-sm border-1 border-slate-200 " placeholder="Email">
          <button v-show="sentence" type="submit" v-on:click="signUp()" class="bg-fuchsia-400 border-fuchsia-400 text-white px-3 py-2 rounded mt-2 text-sm">Unirme</button>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: "CompImagefooter",
  data() {
    return {
      show: false,
      sentence: true
    };
  },
  methods: {
    signUp() {
      this.show = !this.show;
        alert("¡Bienvenid@! Ya formas parte de nuestra comunidad");
      this.sentence = !this.sentence;
    },
  },
};
</script>

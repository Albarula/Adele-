<template>
  <div class="flex flex-row grid-rows-3 bg-black">
    <div class="text-white mx-5">
      <img src="../assets/adeleabout.png" />
      <!--¿ podemos poner un carrousel??-->
    </div>
    <div id="info-bio" class="col-span-2 text-white my-4">
      <h1 class="text-4xl font-serif mt-9 mb-5">ABOUT</h1>
      <div class="text-2xl mt-8 mr-6 pr-7">
        <p>
          Cantante y compositora británica que saltó a la fama gracias a su
          distintiva voz y canciones elaboradas que la convirtieron en una de
          las intérpretes más populares de su generación.
        </p>
        <br />
        <p>
          Lanzó su primer álbum «19» en 2008, que debutó en el número 1 de la
          lista de álbumes británica. Se convirtió en una de las artistas más
          vendidas con ventas que superan los 120 millones de discos.
        </p>
        <br />
        <p>
          El 15 de octubre de 2021, Adele estrenó Easy On Me, la primera canción
          de su esperado cuarto álbum, 30, que aparece el 19 de noviembre de
          este año poniendo fin a más de cinco años de espera.
        </p>
        <br />
        <div>
          <p class="italic text-center mt-7">
            " I don’t make music for eyes. <br />
            I make music for ears”"
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AboutAdele",
};
</script>

<style scoped>
img {
  width: 75%;
}
</style>

<template>
  <div id="aboutadele" class="flex flex-row grid-rows-3 bg-black h-screen">
    <div class="flex items-end">
      <img src="../assets/adeleabout.png"/>
      <!--¿ podemos poner un carrousel??-->
    </div>
    <div id="info-bio" class="col-span-2 text-white my-4 ml-72">
      <h1 class="text-4xl font-serif mt-9 mb-12">ABOUT</h1>
      <div class="text-lg font-thin mt-8 mr-6 pr-7 overflow-y-scroll h-96 bg-neutral-900 rounded w-5/6">
        <p class="ml-3 mb-3">
          Cantante y compositora británica que saltó a la fama gracias a su
          distintiva voz y canciones elaboradas que la convirtieron en una de
          las intérpretes más populares de su generación.
        </p>
        <br />
        <p class="ml-3">
          Comenzó a cantar a los cuatro años teniendo a las Spice Girls como su
          influencia más importante; declaró que cuando su Spice Girl favorita,
          Geri Halliwell dejó el grupo, le rompió el corazón.
        </p>
        <br/>
        <p class="ml-3">
          La salida a la venta de su primer sencillo, Chasing Pavements, la 
          consagró como firme promesa y la llevó al segundo puesto de los superventas.
          Al cabo de un año, fue invitada a compartir escenario con Björk y Paul 
          McCartney en el programa de televisión de Jools Holland, un popular show 
          que seguía en su adolescencia junto a su madre.
        </p>
        <br/>
        <p class="ml-3">
          Lanzó su primer álbum «19» en 2008, que debutó en el número 1 de la
          lista de álbumes británica. Se convirtió en una de las artistas más
          vendidas con ventas que superan los 120 millones de discos.
        </p>
        <br/>
        <p class="ml-3">
          Su segundo trabajo de estudio al que llamó 21, se lanzó en enero de 
          2011 con once temas escritos por ella; un mes después se publicó en
          Estados Unidos. El disco recibió elogios de la crítica y fue un éxito
          comercial: en la primera semana vendió 208.000 copias en el mercado
          británico y 352.000 en el estadounidense convirtiéndose en el cuarto
          álbum más vendido de todos los tiempos.
        </p>
        <br/>
        <p class="ml-3">
          Con 27 años presentó su nuevo álbum titulado 25, en un inesperado anuncio
          en su página de Facebook tras un largo paréntesis creativo. "Mi último
          álbum fue un disco de ruptura, y si tuviera que definir este lo haría
          como un disco de reconciliación", escribió. "Estoy haciendo las paces
          conmigo misma y por el tiempo perdido, reconciliándome con todo lo que
          hice y lo que no hice".
        </p>
        <br/>
        <p class="ml-3">
          La cantante británica triunfó en la entrega de Grammy celebrada el 12 de
          febrero de 2017 al llevarse los cinco premios a los que aspiraba, entre
          ellos el mejor álbum del año por 25, mejor grabación del año y mejor canción,
          ambos por el tema Hello.
        </p>
        <br/>
        <p class="ml-3">
          El 15 de octubre de 2021, Adele estrenó Easy On Me, la primera canción
          de su esperado cuarto álbum, 30, que aparece el 19 de noviembre de
          este año poniendo fin a más de cinco años de espera.
        </p>
      </div>
      <div>
          <p class="italic text-center font-serif text-4xl mt-24 mr-24">
            “ I don’t make music for eyes. <br />
              I make music for ears ”
          </p>
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

<template>

<header id="headele" class="lg:bg-[url('../assets/2ADELE.png')] bg-black lg:h-screen bg-cover bg-no-repeat">
    <nav class="p-3">
        <div class="container flex flex-wrap justify-between items-center mx-auto mt-2.5">
            <a href="headele" class="flex items-center">
                <img src="../assets/1ADELE.png" class="mr-3 h-6 sm:h-10 md:h-14 lg:h-24" alt="Adele Logo" />
            </a>
            <button data-collapse-toggle="navbar-solid-bg" type="button" class="inline-flex justify-center items-center ml-3 text-gray-400 rounded-lg md:hidden hover:text-gray-900 focus:outline-none focus:ring-2 focus:ring-blue-300" aria-controls="navbar-solid-bg" aria-expanded="false">
            <span class="sr-only">Open main menu</span>
            <svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd"></path></svg>
            </button>
            <div class="hidden w-full md:block md:w-auto" id="navbar-solid-bg">
            <ul class="flex flex-col mt-4 bg-gray-50 rounded-lg md:flex-row md:space-x-12 md:mt-0 md:text-sm md:font-medium md:border-0 md:bg-transparent">
                <li>
                    <a href="#concertscomp" class="block py-2 pr-4 pl-3 text-white/70 text-base font-thin rounded hover:bg-grey-100 md:hover:bg-transparent md:border-0 md:hover:text-fuchsia-300 md:p-0">CONCIERTOS</a>
                </li>
                <li>
                    <a href="#albumscomp" class="block py-2 pr-4 pl-3 text-white/70 text-base font-thin rounded hover:bg-grey-100 md:hover:bg-transparent md:border-0 md:hover:text-fuchsia-300 md:p-0">ÁLBUMS</a>
                </li>
                <li>
                    <a href="#aboutadele" class="block py-2 pr-4 pl-3 text-white/70 text-base font-thin rounded hover:bg-grey-100 md:hover:bg-transparent md:border-0 md:hover:text-fuchsia-300 md:p-0">ABOUT</a>
                </li>
            </ul>
            </div>
        </div>
    </nav>
</header>
 
</template> 


<script>
export default {
  name: 'CompHeader',
  }

</script>




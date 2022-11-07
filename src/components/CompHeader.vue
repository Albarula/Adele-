<template>

<header class="bg-[url('../assets/2ADELE.png')] sm:h-full lg:h-screen bg-cover bg-no-repeat">
    <nav class="p-3 bg-grey-50 rounded border-gray-200 dark:bg-gray-800 dark:border-gray-700 w-full">
        <div class="container flex flex-wrap justify-between items-center mx-auto">
            <a href="#" class="flex items-center">
                <img src="../assets/1ADELE.png" class="mr-3 h-6 sm:h-10 md:h-14 lg:h-24" alt="Adele Logo" />
            </a>
            <button data-collapse-toggle="navbar-solid-bg" type="button" class="inline-flex justify-center items-center ml-3 text-gray-400 rounded-lg md:hidden hover:text-gray-900 focus:outline-none focus:ring-2 focus:ring-blue-300 dark:text-gray-400 dark:hover:text-white dark:focus:ring-gray-500" aria-controls="navbar-solid-bg" aria-expanded="false">
            <span class="sr-only">Open main menu</span>
            <svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd"></path></svg>
            </button>
            <div class="hidden w-full md:block md:w-auto" id="navbar-solid-bg">
            <ul class="flex flex-col mt-4 bg-gray-50 rounded-lg md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium md:border-0 md:bg-transparent dark:bg-gray-800 md:dark:bg-transparent dark:border-gray-700">
                <li>
                <a href="#footeradele" class="block py-2 pr-4 pl-3 text-white/50 rounded hover:bg-grey-100 md:hover:bg-transparent md:border-0 md:hover:text-red-300 md:p-0">CONCIERTOS</a>
                </li>
                <li>
                <a href="#adelefooter" class="block py-2 pr-4 pl-3 text-white rounded hover:bg-grey-100 md:hover:bg-transparent md:border-0 md:hover:text-red-200 md:p-0">ÁLBUMS</a>
                </li>
                <li>
                <a href="#" class="block py-2 pr-4 pl-3 text-white rounded hover:bg-grey-100 md:hover:bg-transparent md:border-0 md:hover:text-red-200 md:p-0">ABOUT</a>
                </li>
            </ul>
            </div>
        </div>
    </nav>
</header>
 
        
        <!-- <img class="bg-none" alt="adele1" src="../assets/2ADELE.png"> -->
        <!-- <div id="barra">
            <img alt="logo" src="../assets/1ADELE.png">
            <nav>
            <a id="holi" href="#">CONCIERTOS</a>
            <a href="#">ÁLBUMS</a>
            <a href="#">ABOUT</a>
            </nav>
        </div> 

    </header> -->

</template> 


<script>
export default {
  name: 'CompHeader',
  }

</script>




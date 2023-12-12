<script setup>

let array = ['#titanic','#millonarios','#finalsemtestre','#UFC','#ColombiaMarcha','#UFPSO'];

let arrayChats = [
  {
    name: 'Pedro Pablo',
    time: 'Hace 10 minutos',
  },
  {
    name: 'Felipe Pinto 77',
    time: 'Hace un mes'
  },
  {
    name: 'COCO 77',
    time: 'Hace dos mes'
  },
  {
    name: 'Gisela',
    time: 'Hace un año'
  }
]

const timeDay = new Date();
const hours = timeDay.toLocaleString()


</script>

<template>
  <div class="flex bg-slate-400 w-screen h-screen">

    <div class="bg-slate-900 w-[8%]">
      <img src="../src/img/descarga.jpg" alt="" class="h-24 w-24 mx-auto mt-2 rounded">
      <h2 class="text-center text-gray-300">Perfil</h2>
    </div>

    <div class="bg-slate-800 w-[25%] px-10 py-20 font-semibold text-white">
      
      <h1 class="text-4xl mb-6">TENDENCIAS</h1>
      <h2 v-for="(i, index) in array" :key="index" class="mt-2">{{ i }}</h2>
      <h1 class="text-2xl mt-24 mb-8">MENSAJES DIRECTOS</h1>
      
      <div class="bg-slate-700 flex py-2 px-2 rounded mb-2 hover:cursor-pointer" v-for="(e, index) in arrayChats" :key="index">
        
        <img src="../src/img/descarga.jpg" alt="" class="h-16 w-16 rounded-full"> 
        
        <div class="ml-3 items-center my-auto" >
          <h2 class="text-3xl">{{ e.name }}</h2>
          <h4 class="text-sm">{{ e.time }}</h4>
        </div>

      </div>


    </div>

    <div class="bg-slate-700 p-8 w-[47%]">
      
      <div class="bg-blue-500 h-auto w-auto flex min-w-screen-sm">

        
        <h1 class="bg-white">hola, espero que estes muy bien y que pasaras un lindo día</h1>
        

        <div class="items-end">
          <h1 class="ml-2">{{ hours }}</h1>
        </div>

      </div>

    </div>

    <div class="bg-slate-900 w-[20%]">
      t
    </div>

  </div>
</template>


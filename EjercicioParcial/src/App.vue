<script setup>

let array = ['#titanic','#millonarios','#finalsemtestre','#UFC','#ColombiaMarcha','#UFPSO'];

let arrayChats = [
  {
    name: 'Pedro Pablo',
    time: 'Hace 10 minutos',
    photo: URL('https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.lasexta.com%2Fmotor%2Fsupercoches%2Fkoenigsegg-anticipa-imagen-final-futuro-deportivo-mas-rapido-planeta_2022042562670e0e2dc8df00019076af.html&psig=AOvVaw2QwJvn0UNiWUVjxyhJ4vOo&ust=1702419135697000&source=images&cd=vfe&opi=89978449&ved=0CA8QjRxqFwoTCICniLy2iIMDFQAAAAAdAAAAABAD')
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

/*<img src="../src/img/descarga.jpg" alt="" class="h-16 w-16 rounded-full"> */

</script>

<template>
  <div class="flex bg-slate-400 w-screen h-screen">

    <div class="bg-slate-900 w-[8%]">
      <img src="../src/img/descarga.jpg" alt="" class="h-24 w-24 mx-auto mt-2 rounded">
      <h2 class="text-center text-gray-300">Perfil</h2>
    </div>

    <div class="bg-red-400 w-[25%] px-10 py-20 font-semibold">
      
      <h1 class="text-4xl mb-6">TENDENCIAS</h1>
      <h2 v-for="(i, index) in array" :key="index" class="mt-2">{{ i }}</h2>
      <h1 class="text-2xl mt-24 mb-8">MENSAJES DIRECTOS</h1>
      
      <div class="bg-red-300 flex py-2 px-2 rounded mb-2" v-for="(e, index) in arrayChats" :key="index">
        
        <div>{{e.photo}}</div>
        
        <div class="ml-3 items-center my-auto" >
          <h2 class="text-3xl">{{ e.name }}</h2>
          <h4 class="text-sm">{{ e.time }}</h4>
        </div>

      </div>


    </div>

    <div class="bg-blue-300 w-[47%]">
      y
    </div>

    <div class="bg-gray-100 w-[20%]">
      t
    </div>

  </div>
</template>


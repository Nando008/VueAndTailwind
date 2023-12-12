<script setup>

import { ref } from 'vue';

let personOne = ref(true)
let personTwo = ref(false)
let personThree = ref(false)

let array = ['#titanic','#millonarios','#finalsemtestre','#UFC','#ColombiaMarcha','#UFPSO'];

let arrayChats = [
  {
    name: 'Pedro Pablo',
    time: 'Hace 10 minutos',
  },
  {
    name: 'Felipe Pinto',
    time: 'Hace un mes'
  },
  {
    name: 'Maralad',
    time: 'Hace un año'
  }
]

let mensajes = [
  {
    mensajePerOne: 'hola, espero que estes muy bien y que pasaras un lindo día ',
    mensajePerTwo: 'Bonjour, jespère que vous allez bien et que vous passez une bonne journée.',
    mensajePerthree: 'Hello, I hope you are well and have a nice day.'
  },
  {
    mensajePerOne: 'hola, buenas tardes. Apenas puedas llamame',
    mensajePerTwo: 'Bonjour bon après-midi. Tu peux à peine mappeler',
    mensajePerthree: 'hello, good afternoon. You can barely call me'
  },
  {
    mensajePerOne: 'Mañana va a ser un buen dia',
    mensajePerTwo: 'Demain sera une bonne journée',
    mensajePerthree: 'Tomorrow is going to be a good day'
  }
]

const timeDay = new Date();
const hours = timeDay.toLocaleString()



function Person1(index){
  if(index == 0){
    personOne.value = true
    personTwo.value = false
    personThree.value = false
  }

  if(index == 1){
    personOne.value = false
    personTwo.value = true
    personThree.value = false
  }

  if(index == 2){
    personOne.value = false
    personTwo.value = false
    personThree.value = true
  }
  
}

</script>

<template>
  <div class="flex bg-slate-400 w-[100%] h-screen">

    <div class="bg-slate-900 w-[8%]">
      <img src="../src/img/descarga.jpg" alt="" class="h-20 w-20 mx-auto mt-2 rounded">
      <h2 class="text-center text-gray-300">Perfil</h2>
    </div>

    <div class="bg-slate-800 w-[25%] px-10 py-6 font-semibold text-white">
      
      <h1 class="text-4xl mb-4">TENDENCIAS</h1>
      <h2 v-for="(i, index) in array" :key="index" class="mt-0">{{ i }}</h2>
      <h1 class="text-2xl mt-6 mb-3">MENSAJES DIRECTOS</h1>
      
      <div @click="Person1(index)" class="bg-slate-700 flex py-2 px-2 rounded mb-2 hover:border-2 hover:border-red-800 hover:duration-100 hover:cursor-pointer" v-for="(e, index) in arrayChats" :key="index">
        <img src="../src/img/descarga.jpg" alt="" class="h-16 w-16 rounded-full"> 
        <div class="ml-3 items-center my-auto" >
          <h2 class="text-2xl">{{ e.name }}</h2>
          <h4 class="text-sm">{{ e.time }}</h4>
        </div>
      </div>
    </div>

    <div class="bg-slate-700 p-8 w-[47%]">
      
      <div v-show="personOne">
        <h1 class="text-4xl font-semibold mb-4 text-slate-200">Pedro Pablo</h1>

        <div v-show="personOne" v-for="(s, index) in mensajes" :key="index" class="bg-slate-900 mb-3 h-auto w-auto p-4 rounded-lg border-2 shadow-white min-w-screen-sm">
          <h1 class=" font-semibold text-slate-300 ">{{ s.mensajePerOne }}</h1>
          <div class="items-en mt-2 font-semibold text-slate-300">
           <h1 class="ml-2 flex justify-end">{{ hours }}</h1>
          </div>
        </div>
      </div>

      <div v-show="personTwo">
        <h1 class="text-4xl font-semibold mb-4 text-slate-200" >Felipe Pinto</h1>

        <div v-show="personTwo" v-for="(s, index) in mensajes" :key="index" class="bg-slate-900 mb-3 h-auto w-auto p-4 rounded-lg border-2 shadow-white min-w-screen-sm">
          <h1 class=" font-semibold text-slate-300 ">{{ s.mensajePerTwo }}</h1>
          <div class="items-en mt-2 font-semibold text-slate-300">
           <h1 class="ml-2 flex justify-end">{{ hours }}</h1>
          </div>
        </div>
      </div>

      <div v-show="personThree">
        <h1 class="text-4xl font-semibold mb-4 text-slate-200" >Maralad</h1>

        <div v-show="personThree" v-for="(s, index) in mensajes" :key="index" class="bg-slate-900 mb-3 h-auto w-auto p-4 rounded-lg border-2 shadow-white min-w-screen-sm">
          <h1 class=" font-semibold text-slate-300 ">{{ s.mensajePerthree }}</h1>
          <div class="items-en mt-2 font-semibold text-slate-300">
           <h1 class="ml-2 flex justify-end">{{ hours }}</h1>
          </div>
        </div>
      </div>

    </div>

    <div class="bg-slate-900 w-[20%] px-3 py-10">
      
      <h1 class="text-4xl font-semibold text-slate-200">Publicidad</h1>
      <img src="../src/img/xbox.jpg" class="rounded-xl my-4 h-56 w-64" alt="">      
      <img src="../src/img/play.jpg" alt="" class="rounded-xl my-4 h-44 w-64">

    </div>

  </div>
</template>


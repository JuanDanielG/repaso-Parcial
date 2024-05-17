<script setup>
import { ref } from 'vue';

const data = ['Tema1','Tema2','Tema3','Tema4'];

const selectedIndex = ref(0);

function showInfo(i) {     //esta funcion sirve para hacer un switch que muestre  y guarde la caja donde va el texto
   selectedIndex.value = i;
}



</script>

<template>
    <!-- texto 1 -->
    <div class="bg-blue-500 p-1 max-w-60 mt-12 mx-auto rounded text-center font-bold">

        <div v-for="(theme, i) in data" :key="i" class="bg-blue-400 rounded text-center font-bold">

            <h1 @click="showInfo(i)"
                class=" hover:cursor-pointer bg-blue-300 text-white px-1  flex justify-between text-center" :class="{'bg-blue-600': selectedIndex == i}" > {{ theme }}
                 <span class="cursor-pointer font-bold">{{ selectedIndex == i ? '-' : '+' }}</span>

            </h1>

            <div v-show="selectedIndex == i" class="bg-blue-200 p-1 mt-1 font-bold">{{ theme }}
            </div>
        </div>
    </div>
</template>
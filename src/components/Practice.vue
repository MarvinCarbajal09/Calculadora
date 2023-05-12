<script setup lang="ts">
import { ref } from 'vue';

const Name =ref<boolean>(true);
let Numeros = ref<number[]>([1,2,3,4,5,6,7,8,9,10]);

let numeroGuardado =ref<number>(0)
//Funcion filter
//Filtrado números pares
function Filtrado(){
    const numerosPares = Numeros.value.filter((numero)=> numero % 2 !== 0)
    console.log(numerosPares)
    //Retorna un arreglo
    return numerosPares;
}
function AgregarNumeros(){
    Numeros.value.push(Numeros.value.length + 1)
}

function NuevoNumero(){
    Numeros.value.map((numero)=>{
        //
        console.log(`${numero} * ${numeroGuardado.value} = ${numero * numeroGuardado.value}`)
    })
}

function multiplicarPares(){
    //LLamdo de la funcion filtrado
    Filtrado().map((numero)=>{
        console.log(`${numero} * ${numeroGuardado.value}  ${numero * numeroGuardado.value}`)
    })
}

</script>



<template>
    <!--Llamddo de la función Multiplicar-->
    <button @click ="multiplicarPares">
        Multiplicar
    </button>
    <!--Llamddo de la función Filtrado-->
    <button @click ="Filtrado">
    Filtrar
    </button>
    <button @click="NuevoNumero">
        Fredy
    </button>
    <p>
        {{ Name }}
    </p>
    <input type="text" v-model="numeroGuardado" >
    <button @click="AgregarNumeros" class="DiseñoGuardar">Change</button>
    <ul>
        <li v-for="numero in Numeros">
            {{ numero }}
        </li>
    </ul>
</template>

<style>

</style>
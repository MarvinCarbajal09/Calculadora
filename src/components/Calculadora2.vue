<script setup lang="ts">

import OhVueIcon from "../plugins/oh-vue-icons";
//Importanción
import { ref } from 'vue';

const getOperation = ref<string>('');
const getResult = ref<string>('0');

//AC
function clickAC(){
    getResult.value = '0';
    getOperation.value = ''
}

//DEL
function clickDELL(){
    if (getResult.value.length > 1 ) {
        getResult.value = getResult.value.substring(0, getResult.value.length -1)
} else {
  getResult.value = '0';
}
}

//Funcion click
function click(dato:string){
    if(getResult.value === '0'){
        getResult.value = dato;
    }else{
        getResult.value += dato;
    }
}

//Resultado
function clickResult(){
    let operation = getResult.value;
    getOperation.value = operation;

    operation = operation.replace('x', '*');
    getResult.value = eval(operation)
}

</script>

<template>
    <div class="h-screen bg-white flex justify-center py-16">
    <!--Anchura y altura-->
    <div class="w-1/4"  >
        <!--Emcabezado de la calculadora-->
        <div class="p-4 text-right shadow-2xl rounded-t-lg bg-[#34495E]">
            <h1 class="text-white">2 Calculadora</h1>
            <!--<h1 class="text-[#EBEDEF] bg-[#226DB9] text-center p-10">Calculadora</h1>-->
            <p class="font-simebold text-[#EBEDEF] h-6"> {{ getOperation }} </p>
            <p class="fond-bold text-3xl text-[#EBEDEF] my-2"> {{ getResult }}</p> 
        </div>  
        <!--Contenedor de los numeros-->   
        <div class="mt-1 grid grid-cols-4 gap-1 shadow-2x1 rounded-b-lg">
            <!--Iterior de la calculadora-->
            <button class="text-[#34495E] rounded-md h-16 text-xl font-bold bg-[#32F76B]   
            border-[#5D6D7E] col-span-2 hover:bg-[#D5DBDB] " @click="clickAC()">AC</button>
            
            <button class=" rounded-md h-16 text-xl font-bold bg-[#32F76B] 
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="clickDELL()"><OhVueIcon scale="1.5" name="ri-delete-back-2-fill" color="#34495E"></OhVueIcon></button>

            <button  class=" rounded-md h-16 text-xl font-bold bg-[#32F76B] 
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('÷')"><OhVueIcon scale="1.5" name="fa-divide" color="#34495E" animation="float"></OhVueIcon></button>

            <button class=" rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('7')">7</button>

            <button class="rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('8')">8</button>

            <button class="rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('9')">9</button>

            <button class="rounded-md h-16 text-xl font-bold bg-[#32F76B] 
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('x')"><OhVueIcon scale="1.5" name="fa-times" color="#34495E" animation="float"></OhVueIcon></button>

            <button class="rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('4')">4</button>

            <button class="rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('5')">5</button>

            <button class="rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('6')">6</button>

            <button class="rounded-md h-16 text-xl font-bold bg-[#32F76B] 
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('-')"><OhVueIcon scale="1.5" name="fa-minus" color="#34495E" animation="float"></OhVueIcon></button>

            <button class="rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('3')">3</button>

            <button class="rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('2')">2</button>

            <button class="rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('1')">1</button>

            <button class="rounded-md h-16 text-xl font-bold bg-[#32F76B] 
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('+')"><OhVueIcon scale="1.5" name="fa-plus" color="#34495E" animation="float"></OhVueIcon></button>

            <button class="rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] col-span-2  hover:bg-[#D5DBDB] rounded-bl-lg" @click="click('0')">0</button>

            <button class="rounded-md h-16 text-xl font-bold bg-white
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="click('.')">.</button>

            <button class="rounded-md h-16 text-xl font-bold bg-[#32F76B] 
            border-[#5D6D7E] hover:bg-[#D5DBDB]" @click="clickResult()"><OhVueIcon scale="1.5" name="fa-equals" color="#34495E" animation="float"></OhVueIcon></button>
        </div>
    </div>
    </div>
</template>

//Sombreado las linea de los
<style>
button{
    border: 2px solid;
}

</style>
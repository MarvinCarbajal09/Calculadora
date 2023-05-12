<script setup lang="ts">
let numer1 = 4;
let numer2 = 8;

if (numer1 <= numer2 ) {
  console.log(
    "La condicion es correcta el " + numer1 + " es menor que " + numer2
  );
} else {
  console.log("La condición no se cumple "  + numer1 + " no es menor que " + numer2);
}


numer2 <= numer2 ? console.log('La condicion es verdadera') : console.log('La condicion no se cumple')
</script>

<template>
    <!--Condicion que se no cumple-->
    <p v-if=" numer1 >= numer2">
        Goku
    </p>
    <!--Condicion que se cumple-->
    <p v-if=" numer1 <= numer2 || numer1 != numer2"> 
        Wilfredo Dante Herrera
    </p>

    <h1 v-show="numer1 != numer2">
        Jorge Curioso
    </h1>
</template>

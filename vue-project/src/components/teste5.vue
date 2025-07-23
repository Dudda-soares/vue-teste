<template>
    <div class="componente">
        <p>Valor atual: {{ valor }}</p>
        <button @click="incrementar" type="button">+</button>
        <button @click="decrementar" type="button">-</button>
        <button @click="reset" type="button">reset</button>
    </div>
</template>

<script setup>
import { ref } from 'vue';
 
const valor = ref(0)

const incrementar = () =>{
   valor.value++;
}
const decrementar = () =>{
    valor.value--;
}
const reset = () =>{
    valor.value = 0
}
</script>
<template>
    <div class="componente">
        <input type="Number" placeholder="Digite o Primeiro numero" v-model.number="numero1"/>
        <input type="Number" placeholder="Digite o Segundo numero" v-model.number="numero2"/>
        <button type="button" @click="somar">Somar</button>
        <p v-if="total !== null">Resultado : {{ total }}</p>
    </div>
</template>
<script setup>
import { ref } from 'vue';

const numero1 = ref(0)
const numero2 = ref(0)
const total = ref()

const somar = () => {
   
     total.value = numero1.value + numero2.value
}

</script>
<script setup>
import { ref } from 'vue';
const nome = ref('');

const limpar = () => {
  nome.value = '';
}

</script>

<template >
    <div class="componente">
         <label for="">Digite seu nome:</label>
        <input type="text" v-model="nome" placeholder="digite o nome"/>
        <p v-if="nome">{{ nome }} ! Seja bem vinda</p>
        <p v-else>Digite seu nome no campo</p>
        <button type="button" @click="limpar">Limpar</button>
    </div>
 
</template>

<style scoped>

</style>
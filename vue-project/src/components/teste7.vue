<template>
    <div class="componente">
        <h1>lista de itens</h1>
    
    <input type="text" placeholder="digite para filtrar" v-model="filtrar"/>
    <ul>
        <li v-for="(item,index) in itensFiltrados" :key="index">{{ item }}</li>
    </ul>
    <p v-if="itensFiltrados.length === 0">Nao possui dados</p>
    </div>
</template>

<script setup>
import { computed, ref } from 'vue';

const filtrar = ref('');
const itens = ref([
    'Banana',
    'Maçã',
    'Laranja',
    'Abacaxi',
    'Melancia',
    'Uva',
]);

const itensFiltrados = computed(()=>{

      return itens.value.filter(item => item.toLowerCase().includes(filtrar.value.toLowerCase()))
    }
)
</script>
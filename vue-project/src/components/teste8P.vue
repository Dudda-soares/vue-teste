<template>

    <li> {{ nome }}, {{ idade }}</li>
    <button type="button" @click="adicionar">Avisou</button>
   
</template>
<script setup>
 
import { defineProps, defineEmits } from 'vue';
 
const props = defineProps({
    nome: String,
    idade:Number
})

 const emit = defineEmits(['Clicou'])

 const adicionar = (nome) =>{
    emit('Clicou', props.nome)
 }


</script>
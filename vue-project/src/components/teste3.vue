<template>
    <div class="componente">
        <label for="">Selecione o periodo</label>
        <select v-model="parteDoDia">
            <option value="manha">Manhã</option>
            <option value="tarde">Tarde</option>
            <option value="noite">Noite</option>
        </select> <br/>
        <label for="">Nome: </label>
        <input type="text" placeholder="Digite seu nome:" v-model="nome"/>
        <p v-if="nome && parteDoDia">Boa {{ parteDoDia }} {{ emoji }}, {{ nome }}</p>
    </div>
</template>

<script setup>
import { computed, ref } from 'vue';

const nome = ref('')

const parteDoDia = ref('')

const emoji = computed(()=>{

    switch(parteDoDia.value){
        case 'manha':
            return '☀️';
        case 'tarde':
            return '🌇';
        case 'noite':
            return '🌙'
        
    }
    return '';  
})



</script>

<style scoped>
    
    label,input{
        margin: 18px;
    }
</style>
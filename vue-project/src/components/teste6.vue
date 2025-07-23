<template>
    <div class="componente">
        <label for="">Digite uma tarefa </label>
        <input type="text" placeholder="tarefa" v-model="novaTarefa"/>
        <ul>
            <li v-for="(tarefa,index) in tarefas" :key="index" @click="removerTarefa(index)">{{ tarefa }}</li>
        </ul>
        <button type="button" @click="adicionar">Adicionar</button>
        <p v-if="tarefas.length=== 0">Nenhuma tarefa add</p>
    </div>
</template>
<script setup>
import { ref } from 'vue';

const novaTarefa = ref('')
const tarefas = ref([])

const adicionar = () =>{

   tarefas.value.push(novaTarefa.value)
    novaTarefa.value = ''

}
const removerTarefa = (index) =>{
    
    tarefas.value.splice(index)
}
</script>
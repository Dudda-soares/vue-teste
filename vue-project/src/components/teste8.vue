    <template>
        <div class="componente">
            <h1>Lista de Pessoas</h1>
            <label>
                <input type="checkbox" v-model="apenasMaiores"/>
                Mostrar apenas Maiores de Idade 
            </label>
            <ul>
                <p>Total {{ pessoasFiltradas.length }}</p>
                <teste8-p 
                v-for="(pessoa, index ) in pessoasFiltradas" 
                :key="index" 
                :nome="pessoa.nome" 
                :idade="pessoa.idade"
                @-clicou="mostrarAlerta"
                />
             
            </ul>
            <p v-if="pessoasFiltradas.length === 0">Não encontrado</p>
        </div>
    </template>


    <script setup>
    import teste8P from './teste8P.vue';
    import { computed, ref } from 'vue';
    

    const apenasMaiores = ref(false);
    const pessoas = ref([
        {nome:'Eduarda', idade: 26},
        {nome:'Francisco', idade: 27},
        {nome:'Diana', idade: 20},
        {nome:'Nami', idade: 18},
        {nome:'Robi', idade: 14},
        {nome:'Vivi', idade: 10}
    ])
    const pessoasFiltradas = computed(()=>{
       return pessoas.value.filter(pessoa => !apenasMaiores.value || pessoa.idade >= 18)
       
    })

    const mostrarAlerta = (nome) =>{
        alert(`Voce clicou em ${nome}`)
    }
 
    </script>
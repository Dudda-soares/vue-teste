<template>
    <div class="componente">
        <button type="button" @click="status"> Status</button>
        <p v-if="online">Voce esta On</p>
        <p v-else>voce esta off</p>
    </div>
</template>
<script setup>
import { ref } from 'vue';

const online = ref(false);

const status = ()  =>{
    online.value = !online.value
}
</script>
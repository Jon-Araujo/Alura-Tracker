<template>
    <BoxLista>
        <div class="columns">
            <div class="column is-7">
                {{tarefa.descricao}}
            </div>
            <div class="column">
                <CronometroTempo :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </BoxLista>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import CronometroTempo from './CronometroTempo.vue';
import ITarefa from '@/interfaces/ITarefa';
import BoxLista from './BoxLista.vue';

export default defineComponent({
    name: "TarefaNova",
    components: {
    CronometroTempo,
    BoxLista
},
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
})
</script>

<style scoped>
    
</style>
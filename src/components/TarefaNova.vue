<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                {{tarefa.descricao}}
            </div>
            <div class="column">
                <CronometroTempo :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import CronometroTempo from './CronometroTempo.vue';
import ITarefa from '@/interfaces/ITarefa';

export default defineComponent({
    name: "TarefaNova",
    components: {
        CronometroTempo
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
    .box {
        background: #FAF0CA
    }
</style>
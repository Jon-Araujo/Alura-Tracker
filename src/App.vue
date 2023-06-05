<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <FormularioTarefas @aoSalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <TarefaNova v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

import BarraLateral from './components/BarraLateral.vue';
import FormularioTarefas from './components/FormularioTarefas.vue';
import TarefaNova from './components/TarefaNova.vue';
import ITarefa from './interfaces/ITarefa';


export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormularioTarefas,
    TarefaNova
  },
  data () {
    return {
      tarefas: [] as ITarefa[]
    }
  },
  methods: {
    salvarTarefa (tarefa: ITarefa) {
      this.tarefas.push(tarefa)
    }
  }
});
</script>

<style>

</style>

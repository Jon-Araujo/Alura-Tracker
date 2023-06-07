<template>
  <main class="columns is-gapless is-multiline" :class="{ 'modo-escuro': modoEscuro }">
    <div class="column is-one-quarter">
      <BarraLateral @aoTemaAlterado="mudarTema" />
    </div>
    <div class="column is-three-quarter conteudo">
      <FormularioTarefas @aoSalvarTarefa="salvarTarefa" />
      <div class="lista">
        <TarefaNova v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa" />
        <BoxLista v-if="listaVazia">
          Você não está muito produtivo hoje! :(
        </BoxLista>
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
import BoxLista from './components/BoxLista.vue';


export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormularioTarefas,
    TarefaNova,
    BoxLista
  },
  data() {
    return {
      tarefas: [] as ITarefa[],
      modoEscuro: false
    }
  },
  computed: {
    listaVazia () : boolean {
      return this.tarefas.length === 0
    }
  },
  methods: {
    salvarTarefa(tarefa: ITarefa) {
      this.tarefas.push(tarefa)
    },
    mudarTema(modoEscuro: boolean) {
      this.modoEscuro = modoEscuro;
    }
  }
});
</script>

<style>
.lista {
  padding: 1.25rem;
}

main {
  --bg-primario: #FFFFFF;
  --texto-primario: #000000;
}

main.modo-escuro {
  --bg-primario: #2b2d42;
  --texto-primario: #DDDDDD;
}

.conteudo {
  background-color: var(--bg-primario);
}
</style>

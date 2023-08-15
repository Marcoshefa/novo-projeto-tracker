<template>
  <main class="columns is-gapless is-multiline">
    <div class= "colunn is-one-quarter">
      <BarraLateral />
    </div>
    <!-- <div class= "colunn is-full"> -->
    <div class= "colunn is-three-quarter">
      <FormularioTarefas @aoSalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <TarefaP />
        <TarefaP />
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue'
import FormularioTarefas from './components/FormularioTarefas.vue'
import TarefaP from './components/TarefaP.vue'
import ITarefa from './interfaces/ITarefa'

export default defineComponent({
  name: 'App',
  components: {
  BarraLateral,
  FormularioTarefas,
  TarefaP
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
header {
  padding: 1rem;
  background: #0d3b66;
  width: 100%;
  height: 100vh;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
.lista {
  padding: 1.25 rem
}
</style>

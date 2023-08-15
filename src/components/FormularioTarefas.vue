<template>
    <div class="box">
        <div class="columns">
            <div 
                class="column is-8" 
                role="form" 
                area-label="Formulário para criação de uma nova tarefa"
            >
                <input 
                    type="text" 
                    class="input" 
                    placeholder="Qual tarefa você deseja iniciar?"
                    v-model="descricao"
                />
            </div>
            <div class="column">
                <TemporizadorTempo @aoTemporizadorFinalizado="finalizarTarefa"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import TemporizadorTempo from './TemporizadorTempo.vue'

export default defineComponent ({
    name: "FormularioTarefas",
    emits: ['aoSalvarTarefa'],
    components: {
        TemporizadorTempo
    },
    data () {
        return {
            descricao: ''
        }
    },
    methods: {
        finalizarTarefa (tempoDecorrido: number) : void {
            this.$emit('aoSalvarTarefa', {
                duraçãoEmSegundos: tempoDecorrido,
                descricao: this.descricao
            })
            this.descricao = ''
        }
    }
})
</script>

<style>
.box {
    width: 1300px;
}
</style>
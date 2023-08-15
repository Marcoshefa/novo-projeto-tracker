<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                Descrição da tarefa
            </div>
            <div class="column">
                <TempoCronometro :tempoEmSegundos="15"/>
            </div>
        </div>
    </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import TempoCronometro from './TempoCronometro.vue'


export default defineComponent({
    name: 'TarefaP',
    components: {
        TempoCronometro
    }
})
</script>

<style scoped>
.box {
    background: #FAf0CA;
    padding: auto;
    align-items: right;
}
</style>

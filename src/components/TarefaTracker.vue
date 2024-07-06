<template>
  <BoxLista>
    <div class="column is-7">
      {{ tarefa.descricao || "Tarefa sem descrição" }}
    </div>
    <div class="column">
      <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos" />
    </div>
  </BoxLista>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import Cronometro from "./CronometroTracker.vue";
import ITarefa from "../interfaces/ITarefa";
import BoxLista from "./BoxLista.vue";

export default defineComponent({
  name: "TarefaTracker",
  components: {
    Cronometro,
    BoxLista,
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true,
    },
  },
});
</script>

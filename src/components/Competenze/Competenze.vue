<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <section class="competenze">
    <h1>COMPETENZE</h1>
    <div class="lista_competenze">
      <template v-for="competenza in competenze" :key="competenza">
        <SingolaCompetenza :competenza="competenza" />
      </template>
    </div>
  </section>
</template>

<script lang="ts">
import { COMPETENZE } from "@/data/competenze";
import { defineComponent } from "vue";
import SingolaCompetenza from "./SingolaCompetenza.vue";

export default defineComponent({
  components: {
    SingolaCompetenza,
  },
  setup() {
    let competenze: string[] = COMPETENZE;

    return { competenze };
  },
});
</script>

<style>
.competenze h1 {
  width: fit-content;
  font-family: Readex Pro;
  font-size: 3rem;
  font-weight: lighter;
}

.lista_competenze {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  /*   min-width: 50%; */
  gap: 36px;
  justify-items: center;
  align-items: center;
}

.lista_competenze div {
  width: 75%;
  height: 100%;
}

/* Media */
@media screen and (max-width: 600px) {
  .competenze h1 {
    width: 100%;
    text-align: center;
    font-size: 2em;
    font-weight: 570;
  }

  .lista_competenze {
    grid-template-columns: 1fr 1fr;
  }
}
</style>
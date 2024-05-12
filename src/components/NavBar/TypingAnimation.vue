<template>
  <span class="job" v-html="finalText"></span>
</template>

<script lang="ts">
import { defineComponent, Ref, ref } from "vue";

export default defineComponent({
  setup() {
    let textToTrasform = "-Ciao, sono Alessio Fischetti\nun Frontend Web Developer focalizzato nella creazione di Siti e Applicazioni Web";
    let index = 0;
    let finalText: Ref<string> = ref("");

    /* Scrive il testo */
    function trasformText() {
      const delay = 100;

      textToTrasform.charAt(index) == "-" ? (finalText.value += "<b class='title'>") : (finalText.value += textToTrasform.charAt(index));

      if (textToTrasform.charAt(index) == "\n") {
        finalText.value += "<br></b>";
      }

      index++;

      if (index <= textToTrasform.length) {
        setTimeout(trasformText, delay);
      }
    }
    trasformText();

    return { finalText };
  },
});
</script>

<style>
/* Titolo e lavoro */
.title,
.job {
  font-family: Readex Pro;
}

.title {
  font-size: 2.1rem;
  font-weight: bold;
  padding: 1% 0;
}

.job {
  max-width: 70%;
  width: fit-content;
  font-size: 1.7rem;
  margin: 0;
  z-index: 10;
}

/* Animazione Cursore */
.job::after {
  content: "";
  display: inline-block;
  height: 1em;
  padding-left: 2px;
  bottom: 0;
  overflow: hidden;
  animation: typing 800ms infinite;
}

@keyframes typing {
  from {
    border-right: 1px black solid;
  }
  to {
    border-right: none;
  }
}

</style>

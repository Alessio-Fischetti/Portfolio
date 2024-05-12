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
  font-size: 2rem;
  font-weight: bold;
  padding: 1% 0;
}

.job {
  width: fit-content;
  font-size: 1.7rem;
  margin: 0;
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

@media (min-width: 320px) {
  /* smartphones, iPhone, portrait 480x320 phones */
  .title {
    font-size: 1.2em;
  }
  .title_job {
    transform: translatey(-25px);
  }
}

@media (min-width: 280px) {
  /* portrait e-readers (Nook/Kindle), smaller tablets @ 600 or @ 640 wide. */
  .job {
    max-width: 100%;
  }
}
@media (min-width: 641px) {
  /* portrait tablets, portrait iPad, landscape e-readers, landscape 800x480 or 854x480 phones */
  .title {
    font-size: 2em;
  }
  .title_job {
    transform: translatey(-25px);
  }
}
@media (min-width: 912px) {
  /* tablet, landscape iPad, lo-res laptops ands desktops */
  .title {
    font-size: 1.5em;
  }
  .job {
    font-size: 2.2em;
  }
}
@media (min-width: 1024px) {
  /* big landscape tablets, laptops, and desktops */
  .title {
    font-size: 2em;
  }
  .job {
    font-size: 1.7em;
    max-width: 100%;
  }
}
</style>

<template>
  <BackgroundIntroduzione />
  <div class="introduzione_container">
    <div class="introduzione">
      <div class="title_job">
        <TypingAnimation />
        <p class="title">Ciao, sono Alessio Fischetti</p>
        <p class="job">un Frontend Web Developer focalizzato nella creazione di Siti e Applicazioni Web</p>
      </div>
    </div>
    <div class="scroll_suggestion">
      <ScrollSuggestion />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ScrollSuggestion from "../assets/ScrollSuggestion.vue";
import BackgroundIntroduzione from "../assets/BackgroundIntroduzione.vue";
import TypingAnimation from "../shared/TypingAnimation.vue";

export default defineComponent({
  name: "ComponenteIntroduzione",
  components: {
    ScrollSuggestion,
    BackgroundIntroduzione,
    TypingAnimation,
  },
});
</script>

<style>
/* Background Introduzione */
.introduzione_container {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: space-evenly;
}

.introduzione {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
}

/* Titolo e lavoro */
.title,
.job {
  font-family: Readex Pro;
}

.title {
  font-size: 3rem;
  font-weight: bold;
  padding: 1% 0;
}

.job {
  width: 40%;
  font-size: 1.7rem;
  margin: 0;
}

.title_job {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  text-align: center;
  width: 100%;
}

/* Scroll */
.scroll_suggestion {
  margin-bottom: 50px;
}
@media (min-width: 320px) {
  /* smartphones, iPhone, portrait 480x320 phones */
  .title {
    font-size: 2.2em;
  }
  .title_job {
    transform: translatey(-25px);
  }
}

@media (min-width: 280px) {
  /* portrait e-readers (Nook/Kindle), smaller tablets @ 600 or @ 640 wide. */
  .job {
    width: 100%;
  }
}
@media (min-width: 641px) {
  /* portrait tablets, portrait iPad, landscape e-readers, landscape 800x480 or 854x480 phones */
  .title {
    font-size: 3em;
  }
  .title_job {
    transform: translatey(-25px);
  }
}
@media (min-width: 912px) {
  /* tablet, landscape iPad, lo-res laptops ands desktops */
  .title {
    font-size: 4em;
  }
  .job {
    font-size: 2.2em;
  }
}
@media (min-width: 1024px) {
  /* big landscape tablets, laptops, and desktops */
  .title {
    font-size: 3em;
  }
  .job {
    font-size: 1.7em;
    width: 50%;
  }
}
</style>

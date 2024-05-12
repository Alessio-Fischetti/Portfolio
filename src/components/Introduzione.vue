<template>
  <BackgroundIntroduzione />
  <div class="introduzione_container">
    <div class="introduzione">
      <div class="title_job">
        <TypingAnimation />
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
</style>

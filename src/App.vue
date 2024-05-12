<template>
  <NavbarComponent />
  <main>
    <Introduzione id="home" />
    <div class="main_content">
      <AboutMe id="about" />
      <Progetti id="progetti" />
      <Competenze id="competenze" />
    </div>
  </main>
  <FooterComponent />
</template>

<script lang="ts">
import { defineComponent, ref, Ref } from "vue";
import NavbarComponent from "./components/NavBar/NavbarComponent.vue";
import Introduzione from "./components/Introduzione.vue";
import AboutMe from "./components/AboutMe.vue";
import Progetti from "./components/Progetti.vue";
import Competenze from "./components/Competenze/Competenze.vue";
import FooterComponent from "./components/FooterComponent.vue";

export default defineComponent({
  components: {
    NavbarComponent,
    Introduzione,
    AboutMe,
    Progetti,
    Competenze,
    FooterComponent,
  },
  setup() {
    let selected: Ref<string> = ref("progetti");

    return { selected };
  },
});
</script>

<style>
html {
  scroll-behavior: smooth;
  width: 100%;
}
body {
  width: 100%;
  height: 100vh;
  margin: 0;
  background-color: #fafafa;
  position: relative;
}

.navbar_spaceholder {
  height: 90px;
}
.main_content {
  height: 100%;
  padding: 40px;
}

/* Scrollbar */
/* width */
::-webkit-scrollbar {
  width: 8px;
}

/* Track */
::-webkit-scrollbar-track {
  background: #f2f2f2;
  border-radius: 10px;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #acacac;
  border-radius: 10px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555;
}

#progetti {
  padding-top: 70px;
}

/* Anchor behavior */
.about_me,
.competenze,
.progetti {
  scroll-margin-top: 100px;
}

@media screen and (max-width: 600px) {
  main {
    padding: 40px 0 0 0;
  }

  #progetti {
    padding-top: 70px;
  }
}
@media screen and (max-width: 320px) {
  body {
    width: fit-content;
  }
}
</style>

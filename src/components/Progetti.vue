<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h1 class="progetti_titolo">PROGETTI</h1>
    <section class="sezione_progetti">
      <!-- Se lo schermo e' piu' grande utilizza questo carosello -->
      <div v-if="width >= 701">
        <CarouselBigScreen :progetti="progettiDaMostrare" />
      </div>
      <!-- Se lo schermo e' piu' piccolo usa questo carosello -->
      <div v-if="width <= 700" class="small_carousel_container">
        <CarouselSmallScreen :progetti="progettiDaMostrare" />
      </div>
    </section>
  </div>
</template>


<script lang="ts">
import { defineComponent } from "vue";
import CarouselBigScreen from "./DettaglioProgetto/CarouselBigScreen.vue";
import CarouselSmallScreen from "./DettaglioProgetto/CarouselSmallScreen.vue";
import { Progetto } from "@/interfaces/progetto.interface";
import { PROGETTI } from "@/data/progetti";

export default defineComponent({
  components: {
    CarouselBigScreen,
    CarouselSmallScreen,
  },
  setup() {
    const element = document.getElementById("app");
    /* Width della pagina */
    let width: number | undefined;
    /* Recupero dei primi tre progetti */
    let progettiDaMostrare: Progetto[] = PROGETTI;

    return {
      progettiDaMostrare,
      element,
      width,
    };
  },
  created() {
    this.width = document.getElementById("app")?.offsetWidth;
    window.addEventListener("resize", this.myEventHandler);
  },
  unmounted() {
    window.removeEventListener("resize", this.myEventHandler);
  },
  methods: {
    /* Recupera la grandezza della pagina */
    myEventHandler() {
      this.width = this.element?.offsetWidth;
    },
  },
});
</script>



<style>
/* Titolo */
.progetti_titolo {
  width: fit-content;
  font-family: Readex Pro;
  height: fit-content;
  font-size: 3rem;
  font-weight: lighter;
}

.swiper-3d .swiper-slide-shadow-right {
  background-image: linear-gradient(
    to right,
    rgba(0, 0, 0, 1%),
    rgba(0, 0, 0, 0)
  ) !important;
}

.swiper-3d .swiper-slide-shadow-left {
  background-image: linear-gradient(
    to left,
    rgba(0, 0, 0, 1%),
    rgba(0, 0, 0, 0)
  ) !important;
}

.swiper-wrapper:hover {
  cursor: grab;
}

.small_carousel_container {
  width: 100%;
  display: flex;
  justify-content: center;
}

/* Media */
@media screen and (max-width: 1000px) {
  .progetti_titolo {
    width: 100%;
    text-align: center;
    font-size: 2em;
    font-weight: 570;
  }
}
@media screen and (max-width: 450px) {
  .swiper {
    margin: 0 5px;
  }
  .small_carousel_container {
    width: 90%;
  }
}
</style>
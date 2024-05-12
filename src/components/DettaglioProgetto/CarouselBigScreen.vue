<template>
  <swiper
    :effect="'coverflow'"
    :grabCursor="true"
    :centeredSlides="true"
    :slidesPerView="'auto'"
    :coverflowEffect="{
      rotate: 50,
      stretch: 0,
      depth: 100,
      modifier: 1,
      slideShadows: true,
    }"
    :pagination="true"
    :modules="modules"
    class="mySwiper"
  >
    <swiper-slide v-for="progetto in progetti" :key="progetto.id">
      <label class="card">
        <div class="card-content">
          <h3>{{ progetto.titolo }}</h3>
          <p>
            {{ progetto.descrizione }}
          </p>
        </div>
        <div class="git_link">
          <span>Visualizza su </span>
          <a v-bind:href="progetto.gitLink" target="_blank">GitHub</a>
        </div>
      </label></swiper-slide
    >
  </swiper>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { EffectCards, EffectCoverflow } from "swiper/modules";
import "swiper/css";
import "swiper/css/effect-cards";

export default defineComponent({
  name: "CarouselBigScreen",
  props: ["progetti"],
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [EffectCards, EffectCoverflow],
    };
  },
});
</script>

<style scoped>
/* Singola Card */
.card {
  width: 100%;
  height: 100%;
  background: #fff;
  padding: 10px;
  display: flex;
  justify-content: space-around;
  flex-direction: column;
  border-radius: 5%;
  transition: all .2s ease-in-out; 
}

.card h3 {
  font-size: 1.4rem;
}

.card p {
  font-size: medium;
  font-family: Readex Pro;
}

.card p,
h3 {
  text-align: center;
}

.card:hover {
  transform: scale(1.02);
}

/* Link GitHub */
.git_link {
  text-align: center;
  padding-bottom: 5px;
  font-weight: bold;
  font-family: Readex Pro;
}

.git_link a {
  text-decoration: none;
  border-bottom: 1px solid #000;
  padding-bottom: 1px;
  color: black;
}

.git_link a::after {
  color: black;
}

.swiper {
  width: 100%;
  padding-top: 50px;
  padding-bottom: 50px;
}

.swiper-slide {
  width: 300px !important;
  height: 300px !important;
  box-shadow: 3px 20px 11px 0px rgb(0 0 0 / 59%) !important;
}

/* Some swiper class fixes */
.swiper-wrapper {
  justify-content: flex-start;
}
</style>
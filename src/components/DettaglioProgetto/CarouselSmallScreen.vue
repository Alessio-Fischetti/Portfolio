<template>
  <swiper :effect="'cards'" :grabCursor="true" :modules="modules" class="mySwiper">
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
  name: "CarouselSmallScreen",
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
}
.card:hover {
  cursor: grab;
}

.card h3 {
  font-size: 1.4rem;
}

.card p {
  font-size: 0.69em;
  font-family: Readex Pro;
}

.card p,
h3 {
  text-align: center;
}

/* Link GitHub */
.git_link {
  text-align: center;
  padding-bottom: 5px;
  font-weight: bold;
  font-family: Readex Pro;
  font-size: large;
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
  display: flex;
  justify-content: center;
  max-width: 500px;
  width: 100%;
  height: 100%;
  align-items: center;
  justify-content: center;
  border-radius: 18px;
  font-size: 22px;
  font-weight: bold;
  box-shadow: 1px 5px 11px 0px rgb(0 0 0 / 59%);
}

/* Some swiper class fixes */
.swiper-wrapper {
  justify-content: flex-start;
}
/* Media */
@media screen and (max-width: 700px) {
  .swiper {
    width: 260px;
    height: 400px;
  }
}
@media screen and (max-width: 500px) {
  .swiper {
    width: 210px;
    height: 400px;
  }
}
</style>

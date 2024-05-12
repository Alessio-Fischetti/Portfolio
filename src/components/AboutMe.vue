<template>
  <div class="about_me">
    <h1>QUALCOSA SU DI ME</h1>
    <div class="descrizione">
     <!--  <img class="esclamation" src="../assets/PuntoEsclamativo.png" /> -->
      <p>
        Sono un appassionato sviluppatore Front-end dedicato a trasformare idee
        creative in esperienze web coinvolgenti. Con una fervente passione per
        il design e la precisione del codice.
      </p>
    </div>
    <div class="img_holder">
      <img class="working" src="../assets/imgs/placeholder.webp" alt="working" />
    </div>
  </div>
</template>
  
  <script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "AboutMe",
});
</script>

<style>
.about_me h1 {
  width: fit-content;
  font-family: Readex Pro;
  font-size: 3rem;
  font-weight: lighter;
  margin-bottom: 0;
}
/* Descrizione */
.descrizione {
  width: 100%;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.esclamation {
  padding-left: 3%;
  rotate: 5deg;
  margin: 2% 0 2% 7%;
  animation: spin 4s infinite;
  height: 16.5rem;
}

@keyframes spin {
  50% {
    transform: rotate(10deg);
  }
  50% {
    transform: rotate(-10deg);
  }
}

.descrizione p {
  max-width: 480px;
  padding-right: 100px;
  font-family: Readex Pro;
  font-size: 2rem;
  margin: 24px 0;
}

/* Img */
.working {
  width: 60rem;
  max-width: 560.26px;
  max-height: 540px;
  opacity: 0.85;
  transition: all 0.5s;
}
.img_holder {
  padding-left: 100px;
  display: flex;
  justify-content: flex-start;
}

/* Media */
@media screen and (max-width: 1024px) {
  .working {
    max-width: 300px;
  }

  .about_me h1 {
    width: 100%;
    text-align: center;
    font-size: 2rem;
    font-weight: 570;
  }

  .descrizione {
    justify-content: center;
  }

  .descrizione p {
    width: 100%;
    text-align: center;
    padding-right: 0;
    font-family: Readex Pro;
    font-size: larger;
    padding-right: 1%;
  }

  .img_holder {
    padding-left: 0;
    justify-content: center;
  }

  .esclamation{
    padding: 0;
    margin: 0;
    height: 10rem;
  }
}
</style>
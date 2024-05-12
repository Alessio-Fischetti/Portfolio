<template>
  <nav id="navigation_bar">
    <!-- Lato sinistro nav -->
    <div class="contenitore_utente">
      <img
        class="fischetti_alessio"
        src="../../assets/imgs/alessio_nav_photo.jpg"
        alt="Fischetti Alessio's image"
      />
      <h3>ALESSIO FISCHETTI</h3>
    </div>
    <div class="tools">
      <!-- Nav Senza Hamburger -->
      <div v-show="width >= 1029">
        <ul class="senza_ham">
          <li>
            <a href="#home">HOME</a>
          </li>
          <li><a href="#about">ABOUT</a></li>
          <li><a href="#progetti">PROGETTI</a></li>
          <li><a href="#competenze">COMPETENZE</a></li>
        </ul>
      </div>
      <!-- Nav con Hamburger -->
      <div v-show="width <= 1028">
        <Hamburger @click="openCloseHam()" :isOpen="isOpen" />
        <div v-show="isOpen">
          <div class="ham_navigation">
            <ul>
              <li>
                <a href="#home" @click="openCloseHam()">HOME</a>
              </li>
              <li @click="openCloseHam()"><a href="#about">ABOUT</a></li>
              <li><a href="#progetti" @click="openCloseHam()">PROGETTI</a></li>
              <li>
                <a href="#competenze" @click="openCloseHam()">COMPETENZE</a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>


<script lang="ts">
import { defineComponent } from "vue";
import Hamburger from "../../assets/Hamburger.vue";

export default defineComponent({
  components: {
    Hamburger,
  },
  data() {
    const element = document.getElementById("app");

    let width: number | undefined;

    let isOpen = false;

    return { element, width, isOpen };
  },
  /* Creazione ed eliminazione dell' eventHandler */
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

    /* Verifica se l' hamburger e' aperto o meno */
    openCloseHam() {
      this.isOpen = !this.isOpen;
    },
  },
});
</script>

<style>
#navigation_bar {
  z-index: 99;
  position: fixed;
  width: 100%;
  height: 90px;
  background-color: #fff;
  display: flex;
  justify-content: space-between;
  box-shadow: #000 0px -14px 20px;
  transition: top 0.3s;
  top: 0;
}

/* Lato sinistro navbar */
.contenitore_utente {
  display: flex;
  align-items: center;
  gap: 5%;
  padding: 0 0 0 1%;
}

.fischetti_alessio {
  border-radius: 45px;
  height: 5rem;
}

.contenitore_utente h3 {
  font-family: Readex Pro;
  font-size: 1.2rem;
  min-width: fit-content;
}

/* Lato destro navbar ( No Hamburger ) */

.tools {
  width: 50%;
  height: 100%;
}
.senza_ham {
  padding: 0;
  margin: 0;
  height: 90px;
  display: flex;
  justify-content: center;
  align-content: center;
  gap: 10%;
  list-style-type: none;
}

.senza_ham li,
.ham_navigation li {
  font-family: Readex Pro;
  align-self: center;
  font-weight: bold;
}
.senza_ham li:hover,
.ham_navigation li:hover {
  cursor: pointer;
  text-decoration: underline;
  transform: translateY(1px);
}

.senza_ham a,
.ham_navigation a {
  text-decoration: none;
  color: #000;
}

/* Lato destro navbar ( Con Hamburger ) */
.ham_navigation {
  width: 100%;
  height: 0;
  transition: height 1s;
  background-color: #fff;
}

.ham_navigation ul {
  display: flex;
  justify-content: center;
  flex-direction: column;
  margin: 0;
  padding: 0;
  list-style-type: none;
  text-align: rigth;
}

.ham_navigation li {
  width: 90%;
  padding: 4%;
  border-bottom: 0.2px #9f9b9b7e solid;
}

.ham_navigation li:last-child {
  border: none;
  box-shadow: #0000001a 0px 23px 20px;
}

/* Media query */
@media screen and (max-width: 1028px) {
  .contenitore_utente h3 {
    font-size: 1.3rem;
    min-width: auto;
  }

  .tools {
    text-align: right;
    width: 100%;
    position: absolute;
  }

  .ham_navigation {
    transition: height 1s;
    height: fit-content;
  }
}

@media screen and (min-width: 1920px) {
  .senza_ham li,
  .ham_navigation li {
    font-size: 1.5rem;
  }
  .contenitore_utente h3 {
    font-size: 1.6rem;
  }
}
</style>
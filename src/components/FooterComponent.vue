<template>
  <footer>
    <div class="argomenti_footer">
      <div class="descrizione_footer">
        <h2>FISCHETTI ALESSIO</h2>
        <span
          >Sono un appassionato sviluppatore Front-end dedicato a trasformare idee creative in esperienze web coinvolgenti. Con una fervente passione per il design e la precisione del codice.</span
        >
      </div>
      <div class="social_footer">
        <h2>SOCIAL</h2>
        <ul>
          <li>E-MAIL: afischetti.work@gmail.com</li>
          <li>WHATSAPP: +39 380 194 9521</li>
          <li>
            LINKEDIN:
            <a href="https://www.linkedin.com/in/alessio-fischetti-a085ab20a/">Fischetti Alessio</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="copyright">
      <span>© Copyright 2024. Made by Fischetti Alessio</span>
    </div>
  </footer>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "FooterComponent",
});
</script>

<style>
/* Footer */
footer {
  height: 100%;
  background-color: #302e2e;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* Colore testi */
.copyright span,
.descrizione_footer h2,
.descrizione_footer span,
.social_footer h2,
.social_footer li {
  color: #f1e8e8;
}

/* Grandezza titoli */
.descrizione_footer h2,
.social_footer h2 {
  font-family: Readex Pro;
  font-size: 1.5rem;
}

/* Contenitore Argomenti */
.argomenti_footer {
  padding: 4% 0 2% 0;
  margin: 0 auto;
  display: flex;
  justify-content: space-around;
}

/* Descrizione */
.descrizione_footer {
  width: 40%;
}

.descrizione_footer span {
  font-family: Readex Pro;
  font-size: 1rem;
  width: 30%;
}

/* Social */

.social_footer ul {
  padding: 0;
  text-align: left;
  list-style-type: none;
}

.social_footer li {
  font-family: Readex Pro;
  font-size: 1.2rem;
  margin: 15px 0;
}

.social_footer li a {
  text-decoration: none;
  color: #f1e8e8;
}
.social_footer li a:hover {
  text-decoration: underline #f1e8e8;
}

/* Copyright */

.copyright {
  width: 85%;
  padding: 1% 0;
  text-align: center;
  border-top: solid #f1e8e8 1px;
}

.copyright span {
  font-size: 0.8rem;
}
/* Media */
@media screen and (max-width: 800px) {
  .argomenti_footer {
    flex-wrap: wrap;
    flex-direction: column-reverse;
    align-content: center;
  }

  .descrizione_footer {
    width: 80%;
    padding-bottom: 2%;
  }
}

@media screen and (min-width: 1920px) {
  .social_footer li,
  .descrizione_footer span {
    font-size: 1.5rem;
  }

  .descrizione_footer h2,
  .social_footer h2 {
    font-size: 1.6rem;
  }

  .copyright span {
    font-size: 1.3rem;
  }
}
</style>

<template>
  <div class="competenza">
    <i class="fa-brands fa-angular fa-4x" style="color: #b10b0b"></i>
    <p>ANGULAR</p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: ["competenza"],
});
</script>

<style>
.competenza {
  background: linear-gradient(117deg, rgba(255,255,255,1) 36%, rgba(45,118,213,1) 37%);  border-radius: 3%;
  padding: 10px;
  display: flex;
  flex-wrap: wrap;
  align-content: center;
  justify-content: space-around;
  box-shadow: 1px 5px 11px 0px rgb(0 0 0 / 59%);

}

.competenza p {
  display: flex;
  align-self: center;
  font-size: larger;
  font-family: Readex Pro;
  margin: 0;
}

i {
  font-size: large;
  color: red;
  display: flex;
}
</style>
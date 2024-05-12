<template>
  <div class="scroll_body">
    <div class="scroll_dot"></div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({});
</script>

<style>
.scroll_body {
  width: 25px;
  height: 45px;
  border: #000 solid 2px;
  border-radius: 40%;
  display: flex;
  justify-content: center;
}

.scroll_dot {
  width: 6px;
  height: 6px;
  border-radius: 100%;
  background: #000;
  margin: 5px;
  animation: scrolldot 2s infinite;
}

@keyframes scrolldot {
  from {
    align-self: flex-start;
    opacity: 1;
  }
  to {
    transform: translateY(23px);
    opacity: 0;
  }
}
</style>
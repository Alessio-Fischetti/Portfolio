<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <svg
    class="ham hamRotate ham7"
    viewBox="0 0 100 100"
    width="80"
    :class="isOpen ? 'active' : ''"
  >
    <path
      class="line top"
      d="m 70,33 h -40 c 0,0 -6,1.368796 -6,8.5 0,7.131204 6,8.5013 6,8.5013 l 20,-0.0013"
    />
    <path class="line middle" d="m 70,50 h -40" />
    <path
      class="line bottom"
      d="m 69.575405,67.073826 h -40 c -5.592752,0 -6.873604,-9.348582 1.371031,-9.348582 8.244634,0 19.053564,21.797129 19.053564,12.274756 l 0,-40"
    />
  </svg>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: ["isOpen"],
});
</script>

<style>
.ham {
  cursor: pointer;
  -webkit-tap-highlight-color: transparent;
  transition: transform 400ms;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.hamRotate.active {
  transform: rotate(45deg);
}
.hamRotate180.active {
  transform: rotate(180deg);
}
.line {
  fill: none;
  transition: stroke-dasharray 400ms, stroke-dashoffset 400ms;
  stroke: #000;
  stroke-width: 5.5;
  stroke-linecap: round;
}
.ham7 .top {
  stroke-dasharray: 40 82;
}
.ham7 .middle {
  stroke-dasharray: 40 111;
}
.ham7 .bottom {
  stroke-dasharray: 40 161;
}
.ham7.active .top {
  stroke-dasharray: 17 82;
  stroke-dashoffset: -62px;
}
.ham7.active .middle {
  stroke-dashoffset: 23px;
}
.ham7.active .bottom {
  stroke-dashoffset: -83px;
}
</style>
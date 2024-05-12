<template>
  <ul class="background">
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
  </ul>
</template>
<style>
.background {
  position: absolute;
  width: 100%;
  height: 100vh;
  top: 0;
  left: 0;
  margin: 0;
  padding: 0;
  background: #d9d9d9;
  overflow: hidden;
  box-shadow: 1px 1px 11px 0px rgb(0 0 0 / 13%);
}
.background li {
  position: absolute;
  display: block;
  list-style: none;
  width: 20px;
  height: 20px;
  background: rgba(255, 255, 255, 0.2);
  animation: animate 19s linear infinite;
}

.background li:nth-child(0) {
  left: 25%;
  width: 148px;
  height: 148px;
  bottom: -148px;
  animation-delay: 1s;
}
.background li:nth-child(1) {
  left: 52%;
  width: 100px;
  height: 100px;
  bottom: -100px;
  animation-delay: 4s;
}
.background li:nth-child(2) {
  left: 2%;
  width: 346px;
  height: 346px;
  bottom: -346px;
  animation-delay: 6s;
}
.background li:nth-child(3) {
  left: 23%;
  width: 359px;
  height: 359px;
  bottom: -359px;
  animation-delay: 15s;
}
.background li:nth-child(4) {
  left: 19%;
  width: 216px;
  height: 216px;
  bottom: -216px;
  animation-delay: 3s;
}
.background li:nth-child(5) {
  left: 58%;
  width: 205px;
  height: 205px;
  bottom: -205px;
  animation-delay: 5s;
}
.background li:nth-child(6) {
  left: 61%;
  width: 177px;
  height: 177px;
  bottom: -177px;
  animation-delay: 13s;
}
.background li:nth-child(7) {
  left: 10%;
  width: 207px;
  height: 207px;
  bottom: -207px;
  animation-delay: 21s;
}
.background li:nth-child(8) {
  left: 1%;
  width: 454px;
  height: 454px;
  bottom: -454px;
  animation-delay: 27s;
}
.background li:nth-child(9) {
  left: 71%;
  width: 430px;
  height: 430px;
  bottom: -430px;
  animation-delay: 20s;
}

/* Animation Frames */
@keyframes animate {
  0% {
    transform: translateY(0) rotate(0deg);
    opacity: 1;
    border-radius: 0;
  }
  100% {
    transform: translateY(-1000px) rotate(720deg);
    opacity: 0;
    border-radius: 50%;
  }
}
</style>

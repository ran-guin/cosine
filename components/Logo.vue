<template>
  <div class="VueToNuxtLogo">
    <div class="Triangle Triangle--two"/>
    <div class="Triangle Triangle--one"/>
    <div class="Triangle Triangle--three"/>
    <div class="Triangle Triangle--four"/>
  </div>
</template>

<style>
.VueToNuxtLogo {
  display: inline-block;
  animation: turn 2s linear forwards 1s;
  transform: rotateX(180deg);
  position: relative;
  overflow: hidden;
  height: 39px;
  width: 49px;
}

.Triangle {
  position: absolute;
  top: 0;
  left: 0;
  width: 0;
  height: 0;
}

.Triangle--one {
  border-left: 21px solid transparent;
  border-right: 21px solid transparent;
  border-bottom: 36px solid #41b883;
}

.Triangle--two {
  top: 6px;
  left: 7px;
  animation: goright 0.5s linear forwards 3.5s;
  border-left: 16px solid transparent;
  border-right: 16px solid transparent;
  border-bottom: 30px solid #3b8070;
}

.Triangle--three {
  top: 12px;
  left: 7px;
  animation: goright 0.5s linear forwards 3.5s;
  border-left: 14px solid transparent;
  border-right: 14px solid transparent;
  border-bottom: 24px solid #35495e;
}

.Triangle--four {
  top: 24px;
  left: 14px;
  animation: godown 0.5s linear forwards 3s;
  border-left: 7px solid transparent;
  border-right: 7px solid transparent;
  border-bottom: 12px solid #fff;
}

@keyframes turn {
  100% {
    transform: rotateX(0deg);
  }
}

@keyframes godown {
  100% {
    top: 180px;
  }
}

@keyframes goright {
  100% {
    left: 70px;
  }
}
</style>

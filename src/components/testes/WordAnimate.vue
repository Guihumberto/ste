<template>
  <div class="cont">
    <!-- <div class="square">
      <span style="--i:0"></span>
      <span style="--i:1"></span>
      <span style="--i:2"></span>
      <span style="--i:3"></span>
    </div> -->
    <div class="reta">
      <span style="--i:1"></span>
    </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
.cont{
  position: relative;
}
.reta{
  position: absolute;
  width: 200px;
  height: 200px;
  background: yellowgreen;
}
.reta span{
  position: absolute;
  inset: 10px;
  background: blue;
}
.reta span::before{
  content: '';
  position: absolute;
  width: 100%;
  height: 4px;
  background: red;
  animation: anime 4s linear infinite;
}
@keyframes anime {
  0%{
    transform: translateX(-100%);
  }
  50%, 100%{
    transform: translateX(100%);
  }
}
.square{
  position: absolute;
  width: 200px;
  height: 200px;
}
.square span{
  position: absolute;
  inset: 10px;
  overflow: hidden;
  transform: rotate(calc(90deg * var(--i)));
}
.square span::before {
  content: '';
  position: absolute;
  width: 100%;
  height: 4px;
  background: #0f0;
  transform: translateX(-100%);
  animation: animate 4s linear infinite;
  animation-delay: calc(1s * var(--i));
}
@keyframes animate {
  0%{
    transform: translateX(-100%);
  }
  50%, 100%{
    transform: translateX(100%);
  }
}
</style>

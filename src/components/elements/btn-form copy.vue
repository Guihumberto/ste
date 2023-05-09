<template>
  <div>
    <a href="">Enviar</a>
  </div>
</template>

<script setup>

</script>

<style scoped>
 a{
  background: #000;
  position: relative;
  display: inline-block;
  font-size: 1.5em;
  text-decoration: none;
  letter-spacing: .1em;
  color: #0ef;
  text-transform: uppercase;
  border: 2px solid #0ef;
  padding: 10px 30px;
  z-index: 1;
  overflow: hidden;
  transition: color 1s, box-shadow 1s;
 }
 a:hover{
  transition-delay: 0s, 1s;
  color: #fff;
  box-shadow:
    0 0 10px #0ef,
    0 0 20px #0ef,
    0 0 40px #0ef,
    0 0 80px #0ef,
    0 0 160px #0ef;
 }
 a::before {
  content: '';
  position: absolute;
  top: 0;
  left: -50px;
  width: 0%;
  height: 100%;
  background: #0ef;
  transform: skew(35deg);
  transition: 1s;
  z-index: -1;
 }
 a:hover::before{
  width: 100%;
 }
</style>

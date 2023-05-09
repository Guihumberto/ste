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
  color: #fff;
  text-transform: uppercase;
  border: 2px solid #fff;
  padding: 10px 30px;
  z-index: 1;
  overflow: hidden;
  transition: color 1s, box-shadow 1s;
 }
 a:hover{
  transition-delay: 0s, 1s;
  color: #fff;
  box-shadow:
    0 0 10px purple,
    0 0 20px purple,
    0 0 40px purple,
    0 0 80px purple,
    0 0 160px purple;
 }
</style>

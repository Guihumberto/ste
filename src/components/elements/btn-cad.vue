<template>
  <div>
    <a href="">OK</a>
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
  color: #afabab;
  text-transform: uppercase;
  border: 2px solid #fff;
  padding: 6px 15px;
  z-index: 1;
  overflow: hidden;
  transition: color .5s, box-shadow 1s;
 }
 a:hover{
  transition-delay: 0s, 1s;
  color: #fff;
  box-shadow:
    0 0 10px #fff,
    0 0 20px #fff,
    0 0 40px #fff,
    0 0 80px #fff,
    0 0 160px #fff;
 }
</style>

<template>
 <a href="">
    <span></span>
    <span></span>
    Stephane Lima
  </a>
</template>

<script setup>
</script>

<style scoped>
a{
  position: relative;
  font-size: 2.7rem;
  text-decoration: none;
  padding: 10px 20px;
  color: #fff;
  letter-spacing: 1.6px;
  transition: .5s;

}
a:hover {
  color: aqua;
  letter-spacing: 4px;
}
a span {
  position: absolute;
  left: 0;
  bottom: 0;
  display: inline-block;
  background: aqua;
}

a span:first-child {
  width: 3px;
  height: 90%;
  transform: translateX(0);
  opacity: 0;
  transition: .5s;
}
a:hover span:first-child {
  opacity: 1;
  transform: translateX(15px);
}

a span:last-child {
  width: 90%;
  height: 3px;
  transform: translateY(0);
  opacity: 0;
  transition: .5s;
}
a:hover span:last-child {
  opacity: 1;
  transform: translateY(-10px);
}

</style>

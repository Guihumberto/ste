<template>
  <div class="btn">
    <a href="#blog">Mentoria</a>
  </div>
</template>

<script setup>

</script>

<style scoped>
.btn{
  position: relative;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  width: 180px;
  height: 48px;
  border-radius: 40px;
  font-size: 19px;
  color: #fff;
  text-decoration: none;
  font-weight: 600;
  letter-spacing: 1px;
  z-index: 1;
  opacity: 0;
  animation: slideTop 1s ease forwards;
  animation-delay: 1.8s;
}
.btn::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  inset: 0;
  background: linear-gradient(45deg, #f06, #3cf, #f06);
  background-position: 0 0;
  z-index: -1;
  border-radius: 40px;
  background-size: 200%;
  filter: blur(5px);
  transition: .5s ease;
}
.btn::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  inset: 0;
  background: linear-gradient(45deg, #f06, #3cf, #f06);
  background-position: 0 0;
  z-index: -1;
  border-radius: 40px;
  background-size: 200%;
  transition: .5s;
}
.btn:hover::before {
  background-position: 100% 0;
}
.btn:hover::after {
  background-position: 100% 0;
}
.btn a{
  color: #fff;
}
</style>

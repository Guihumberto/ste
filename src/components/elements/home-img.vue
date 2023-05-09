<template>
  <div class="home-img">
    <div class="glowing-circle">
      <span></span>
      <span></span>
      <div class="image">
        <img :src="photoSte" alt="photo ste">
      </div>
    </div>
  </div>
</template>

<script setup>
import photoSte from '../../../public/ste-removebg.png'
</script>

<style scoped>
.home-img{
  width: 410px;
  height: 410px;
  opacity: 0;
  animation: zoomIn 1s ease forwards;
  animation-delay: 2.1s;
}
.glowing-circle{
  position: relative;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.glowing-circle::after {
  content: '';
  position: absolute;
  width: 380px;
  height: 380px;
  background: #0c1022;
  border-radius: 50%;
}
.glowing-circle span{
  position: absolute;
  width: 100%;
  height: 100%;
  background: linear-gradient(#f06, #3cf);
  border-radius: 50%;
  animation: circleRotate 5s linear infinite;
}
.glowing-circle span:nth-child(1){
  filter: blur(10px);
}
.glowing-circle .iconmdi {
  position: relative;
  width: 380px;
  height: 380px;
  background: blue;
  border-radius: 50%;
  z-index: 1;
  overflow: hidden;
}
.glowing-circle .image{
  position: relative;
  width: 380px;
  height: 380px;
  /* background: red; */
  border-radius: 50%;
  z-index: 1;
  overflow: hidden;
}
.image img{
  position: absolute;
  top: 10px;
  left: 50%;
  transform: translateX(-50%);
  max-width: 280px;
  object-fit: cover;
}

@keyframes circleRotate {
  0%{
    transform: rotate(0);
  }
  100%{
    transform: rotate(360deg);
  }
}

@media (max-width: 991px) {
  .home-img{
    display: none;
  }
}

@media (max-width: 600px){
.home-img{
  display: flex;
  margin-bottom: 10px;
  width: 260px;
  height: 260px;
}
.glowing-circle::after {
  content: '';
  position: absolute;
  width: 250px;
  height: 250px;
  background: #0c1022;
  border-radius: 50%;
}
.glowing-circle .iconmdi {
  position: relative;
  width: 250px;
  height: 250px;
  background: blue;
  border-radius: 50%;
  z-index: 1;
  overflow: hidden;
}
.glowing-circle .image{
  position: relative;
  width: 250px;
  height: 250px;
  /* background: red; */
  border-radius: 50%;
  z-index: 1;
  overflow: hidden;
}
.image img{
  position: absolute;
  top: 10px;
  left: 50%;
  transform: translateX(-50%);
  max-width: 200px;
  object-fit: cover;
}
}
</style>
